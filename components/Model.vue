<template>
  <canvas ></canvas>
</template>

<script>
export default {
  methods: {
    animate() {
      requestAnimationFrame(animate);
      renderer.render(scene, camera);
    },

    load3d() {

      var scene = new THREE.Scene();
      if (process.browser) {
        window.onNuxtReady((app) => {
          console.log("Nuxt ready!");
        });
      }
      var camera = new THREE.PerspectiveCamera(75, 0.835, 0.1, 1000);

      var renderer = new THREE.WebGLRenderer();
      renderer.setSize(790, 660);
      document.body.appendChild(renderer.domElement);

      var geometry = new THREE.BoxGeometry();
      var material = new THREE.MeshBasicMaterial({ color: 0x00ff00 });
      var cube = new THREE.Mesh(geometry, material);
      scene.add(cube);

      camera.position.z = 5;

      this.animate();
    },
  },
};
</script>