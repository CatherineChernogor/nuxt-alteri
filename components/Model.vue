<template>
  <div ref="container"></div>
</template>

<script>
import * as THREE from "three";
import { OrbitControls } from "three/examples/jsm/controls/OrbitControls";
import { GLTFLoader } from "three/examples/jsm/loaders/GLTFLoader";

export default {
  props: ["camera", "light", "grid", "modelPath"],

  data() {
    const scene = new THREE.Scene();
    const renderer = new THREE.WebGLRenderer({antialias: true});
    const light = this.getThreeLight(this.light);
    const camera = this.getThreeCamera(this.camera);
    const model = this.modelPath;
    

    return {
        scene_: scene,
        light_: light,
        camera_: camera,
        renderer_:  renderer,
        model_: model,
    };
  },

  watch: {
    modelPath: {
      deep: true,
      handler (v) {
        this.loadAndReplaceObject(v);
      }
    },
    camera: {
      deep: true,
      handler(v) {
        this.updateCamera(v);
      }
    },
    light: {
      deep: true,
      handle(v) {
        this.updateLight(v);
      }
    }
  },

  methods: {

    loadAndReplaceObject(path) {
      if (this.model_) {
        this.scene_.remove(this.model_);
      }

      const loader = new GLTFLoader();
      loader.load(path, (obj) => {
        this.scene_.add(obj.scene);
        this.model_ = obj.scene;
        // console.log(obj);
      });
    },

    getThreeLight(light) {
      const skyColor = light.skyColor;
      const groundColor = light.groundColor;
      const intensity = light.intensity;
      return new THREE.HemisphereLight(
        skyColor,
        groundColor,
        intensity
      );
    },

    getThreeCamera(camera) {
      const fov = camera.fov;
      const aspect = window.innerWidth / window.innerHeight; // the canvas default
      const near = camera.near;
      const far = camera.far;

      const result = new THREE.PerspectiveCamera(fov, aspect, near, far);
      result.position.set(
        camera.positionA,
        camera.positionB,
        camera.positionC
      );

      return result;
    },

    updateCamera(newCamera) {
      this.scene_.remove(this.camera_);
      this.camera_ = this.getThreeCamera(newCamera);
      this.scene_.add(this.camera_);
    },

    updateLight(newLight) {
      this.scene_.remove(this.light_);
      this.light_ = this.getThreeLight(newLight);
      this.scene_.add(this.light_);
    },

    initBackground() {
      //renderer
      {
        var scene = this.scene_;

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

        this.renderer_.setSize(window.innerWidth, window.innerHeight);
      }

      //controls
      {
        var controls = new OrbitControls(this.camera_, this.renderer_.domElement);

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
    },
    animate(){
      requestAnimationFrame(this.animate);
      this.renderer_.render(this.scene_, this.camera_);
    },
  },
  mounted() {
    this.$refs.container.appendChild(this.renderer_.domElement);
    this.initBackground();
    this.updateLight(this.light);
    this.updateCamera(this.camera);
    this.loadAndReplaceObject(this.modelPath);
    this.animate();
  }
};
</script>
