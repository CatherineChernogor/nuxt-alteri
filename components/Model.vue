<template></template>

<script>
import * as THREE from "three";
import { OrbitControls } from "three/examples/jsm/controls/OrbitControls";
import { GLTFLoader } from "three/examples/jsm/loaders/GLTFLoader";
import { OBJLoader2 } from "three/examples/jsm/loaders/OBJLoader2";
import { GUI } from "three/examples/jsm/libs/dat.gui.module";
import { MTLLoader } from "three/examples/jsm/loaders/MTLLoader.js";
import { MtlObjBridge } from "three/examples/jsm/loaders/obj2/bridge/MtlObjBridge.js";

export default {
  methods: {
    canvas() {
      //camera
      {
        const fov = 100;
        const aspect = window.innerWidth / window.innerHeight; // the canvas default
        const near = 0.1;
        const far = 1500;
        var camera = new THREE.PerspectiveCamera(fov, aspect, near, far);

        camera.position.set(1000, 700, 700);
      }

      //control bar
      {
        class MinMaxGUIHelper {
          constructor(obj, minProp, maxProp, minDif) {
            this.obj = obj;
            this.minProp = minProp;
            this.maxProp = maxProp;
            this.minDif = minDif;
          }
          get min() {
            return this.obj[this.minProp];
          }
          set min(v) {
            this.obj[this.minProp] = v;
            this.obj[this.maxProp] = Math.max(
              this.obj[this.maxProp],
              v + this.minDif
            );
          }
          get max() {
            return this.obj[this.maxProp];
          }
          set max(v) {
            this.obj[this.maxProp] = v;
            this.min = this.min; // this will call the min setter
          }
        }

        function updateCamera() {
          camera.updateProjectionMatrix();
        }

        const gui = new GUI();
        gui.add(camera, "fov", 1, 180).onChange(updateCamera);

        const minMaxGUIHelper = new MinMaxGUIHelper(camera, "near", "far", 0.1);
        gui
          .add(minMaxGUIHelper, "min", 0.1, 100, 0.1)
          .name("near")
          .onChange(updateCamera);
        gui
          .add(minMaxGUIHelper, "max", 0.1, 5000, 1)
          .name("far")
          .onChange(updateCamera);
      }

      //renderer
      {
        var scene = new THREE.Scene();
        scene.background = new THREE.Color("pink");

        var renderer = new THREE.WebGLRenderer({ antialias: true });
        renderer.setSize(window.innerWidth, window.innerHeight);
        document.body.appendChild(renderer.domElement);
      }

      //directional lights
      {
        /*
        const color = 0xffffff;
        const intensity = 1;
        const light = new THREE.DirectionalLight(color, intensity);

        light.position.set(0, 10, 0);
        light.target.position.set(-5, 0, 0);
        scene.add(light);
        scene.add(light.target);

        class ColorGUIHelper {
          constructor(object, prop) {
            this.object = object;
            this.prop = prop;
          }
          get value() {
            return `#${this.object[this.prop].getHexString()}`;
          }
          set value(hexString) {
            this.object[this.prop].set(hexString);
          }
        }
/*
        const gui = new GUI();
        gui.addColor(new ColorGUIHelper(light, "color"), "value").name("color");
        gui.add(light, "intensity", 0, 2, 0.01);
        gui.add(light.target.position, "x", -10, 10);
        gui.add(light.target.position, "z", -10, 10);
        gui.add(light.target.position, "y", 0, 10);
//
        const helper = new THREE.DirectionalLightHelper(light);
        scene.add(helper);

        function makeXYZGUI(gui, vector3, name, onChangeFn) {
          const folder = gui.addFolder(name);
          folder.add(vector3, "x", -10, 10).onChange(onChangeFn);
          folder.add(vector3, "y", 0, 10).onChange(onChangeFn);
          folder.add(vector3, "z", -10, 10).onChange(onChangeFn);
          folder.open();
        }

        function updateLight() {
          light.target.updateMatrixWorld();
          helper.update();
        }
        updateLight();

        const gui = new GUI();
        gui.addColor(new ColorGUIHelper(light, "color"), "value").name("color");
        gui.add(light, "intensity", 0, 20, 0.01);

        makeXYZGUI(gui, light.position, "position", updateLight);
        makeXYZGUI(gui, light.target.position, "target", updateLight);
     */
      }

      //hemishere light
      {
        class ColorGUIHelper {
          constructor(object, prop) {
            this.object = object;
            this.prop = prop;
          }
          get value() {
            return `#${this.object[this.prop].getHexString()}`;
          }
          set value(hexString) {
            this.object[this.prop].set(hexString);
          }
        }

        {
          const skyColor = 0xb1e1ff; // light blue
          const groundColor = 0xb97a20; // brownish orange
          const intensity = 1;
          const light = new THREE.HemisphereLight(
            skyColor,
            groundColor,
            intensity
          );
          scene.add(light);

          const gui = new GUI();
          gui
            .addColor(new ColorGUIHelper(light, "color"), "value")
            .name("skyColor");
          gui
            .addColor(new ColorGUIHelper(light, "groundColor"), "value")
            .name("groundColor");
          gui.add(light, "intensity", 0, 10, 0.01);
        }
      }

      //controls
      {
        var controls = new OrbitControls(camera, renderer.domElement);

        controls.enableDamping = true;
        controls.dampingFactor = 0.25;
        controls.enableZoom = true;
        controls.autoRotate = true;
        controls.target.set(0, 5, 0);
      }
      //grid
      {
        const size = 10000;
        const divisions = 100;
        const colorCenterLine = 0xff0000;
        const colorGrid = 0xffffff;
        var gridXZ = new THREE.GridHelper(
          size,
          divisions,
          colorCenterLine,
          colorGrid
        );
        scene.add(gridXZ);
      }

      //loader glft
      {
        const objLoader = new GLTFLoader();
        const url = "model/arland/arland.gltf";
        const url2 = "mod2/ver3.gltf";

        objLoader.load(url2, (obj) => {
          scene.add(obj.scene);
        });
      }

      //load texture
      {
        /*
        {
          const materialURL = "model/arland/arland.obj";
          const objectURL = "model/arland/arland.mtl";

          const mtlLoader = new MTLLoader();

          mtlLoader.load(
            materialURL,
            (mtlParseResult) => {
              const materials = MtlObjBridge.addMaterialsFromMtlLoader(
                mtlParseResult
              );
              const objLoader = new OBJLoader2();

              objLoader.addMaterials(materials);
              objLoader.load(objectURL, 
              (obj) => scene.add(obj),
              (xhr) =>  console.log( 'Model '+  ( xhr.loaded / xhr.total * 100 ) + '% loaded' ),
              (error) =>  console.log(error));
            },
            (xhr) => console.log( 'Material '+  ( xhr.loaded / xhr.total * 100 ) + '% loaded' ),
            (error) => console.log(error)
          );
        }*/
      }
      function animate() {
        controls.update();
        requestAnimationFrame(animate);
        renderer.render(scene, camera);
      }

      animate();
    },
  },
  mounted() {
    this.canvas();
  },
};
</script>

<style lang="scss" scoped>
.split {
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  display: flex;
}
.split > div {
  width: 100%;
  height: 100%;
}
</style>