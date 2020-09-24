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
        const fov = 50;
        const aspect = window.innerWidth / window.innerHeight; // the canvas default
        const near = 0.1;
        const far = 10000;
        var camera = new THREE.PerspectiveCamera(fov, aspect, near, far);

        camera.position.set(3000, 2000, 3000);
        function updateCamera() {
          camera.updateProjectionMatrix();
        }
      }

      //renderer
      {
        var scene = new THREE.Scene();
        scene.background = new THREE.Color("pink");

        var renderer = new THREE.WebGLRenderer({ antialias: true });
        renderer.setSize(window.innerWidth, window.innerHeight);
        document.body.appendChild(renderer.domElement);
      }

      //hemishere light
      {
        const skyColor = 0x989fa3; // light blue
        const groundColor = 0x36322d; // brownish orange
        const intensity = 1.5;
        const light = new THREE.HemisphereLight(
          skyColor,
          groundColor,
          intensity
        );
        scene.add(light);
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
        const loader = new GLTFLoader();
        const url = "model_stand/stand_light.gltf";

        loader.load(url, (obj) => {
          scene.add(obj.scene);
        });
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