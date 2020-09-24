<template></template>

<script>
import * as THREE from "three";
import { OrbitControls } from "three/examples/jsm/controls/OrbitControls";
import { GLTFLoader } from "three/examples/jsm/loaders/GLTFLoader";

export default {
  props: ["camera", "light", "grid", "modelPath"],

  methods: {
    forceRerender() {
      this.componentKey += 1;  
    },
    canvas() {
      console.log(this.camera);
      console.log(this.light);
      console.log(this.grid);
      console.log(this.modelPath);
      //camera
      {
        const fov = this.camera.fov;
        const aspect = window.innerWidth / window.innerHeight; // the canvas default
        const near = this.camera.near;
        const far = this.camera.far;
        var camera = new THREE.PerspectiveCamera(fov, aspect, near, far);

        camera.position.set(
          this.camera.positionA,
          this.camera.positionB,
          this.camera.positionC
        );

        function updateCamera() {
          camera.updateProjectionMatrix();
        }
      }

      //renderer
      {
        var scene = new THREE.Scene();

        const loader = new THREE.TextureLoader();
        const bgTexture = loader.load("background2.jpg");
        // Set the repeat and offset properties of the background texture
        // to keep the image's aspect correct.
        // Note the image may not have loaded yet.
        const canvasAspect = window.innerWidth / window.innerHeight;
        const imageAspect = bgTexture.image
          ? bgTexture.image.width / bgTexture.image.height
          : 1;
        const aspect = imageAspect / canvasAspect;

        bgTexture.offset.x = aspect > 1 ? (1 - 1 / aspect) / 2 : 0;
        bgTexture.repeat.x = aspect > 1 ? 1 / aspect : 1;

        bgTexture.offset.y = aspect > 1 ? 0 : (1 - aspect) / 2;
        bgTexture.repeat.y = aspect > 1 ? 1 : aspect;
        scene.background = bgTexture;
        //scene.background = new THREE.Color("white"); //#FFCCFE

        var renderer = new THREE.WebGLRenderer({
          antialias: true,
        });
        renderer.setSize(window.innerWidth, window.innerHeight);
        document.body.appendChild(renderer.domElement);
      }

      //hemishere light
      {
        const skyColor = this.light.skyColor;
        const groundColor = this.light.groundColor;
        const intensity = this.light.intensity;
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
        const size = this.grid.size;
        const divisions = this.grid.divisions;
        const colorCenterLine = this.grid.colorGrid;
        const colorGrid = this.grid.colorGrid;
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
        const url = this.modelPath;

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
