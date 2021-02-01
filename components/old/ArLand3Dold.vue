<template></template>

<script>
import * as THREE from "three";
import { OrbitControls } from "three/examples/jsm/controls/OrbitControls";
import { GLTFLoader } from "three/examples/jsm/loaders/GLTFLoader";

export default {
  methods: {
    canvas() {
      //camera
      {
        const fov = 60;
        const aspect = window.innerWidth / window.innerHeight; // the canvas default
        const near = 0.1;
        const far = 4000;
        var camera = new THREE.PerspectiveCamera(fov, aspect, near, far);

        camera.position.set(1000, 600, 600);

        function updateCamera() {
          camera.updateProjectionMatrix();
        }
      }

      //renderer
      {
        var scene = new THREE.Scene();

        const loader = new THREE.TextureLoader();
        const bgTexture = loader.load("background2.jpg");
        
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
        const skyColor = 0xb9c8d8;
        const groundColor = 0x711313;
        const intensity = 5;
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
        const size = 2000;
        const divisions = 25;
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
        const url = "model_land/land.gltf";

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
</style>