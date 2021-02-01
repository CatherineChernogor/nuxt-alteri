<template>
  <div>
    <client-only>
      <nuxt-link :to="'/'" exact class="go-back-button highlight"
        >GO BACK</nuxt-link
      >
      <model
        
        :camera="camera"
        :light="light"
        :grid="grid"
        :model-path="modelPath"
        :key="componentKey"
      />
    </client-only>
  </div>
</template>
<script>
export default {
  layout: "empty",
  data: () => ({
    camera: {
      fov: 70,
      near: 0.1,
      far: 4000,
      positionA: 0,
      positionB: 400,
      positionC: 1000,
    },
    light: {
      skyColor: 0xb9c8d8,
      groundColor: 0x711313,
      intensity: 5,
    },
    grid: {
      size: 2000,
      divisions: 25,
      colorCenterLine: 0xff0000,
      colorGrid: 0xffffff,
    },
    modelPath: "model_land/land.gltf",
    componentKey: "ArLand",
  }),
  components: {
    Model: process.browser
      ? () => import("../components/Model.vue")
      : null,
  },
};
</script>
<style lang="scss" scoped>
@import "/assets/css/vars";
.go-back-button {
  display: flex;
  position: absolute;
  width: 175px;
  height: 70px;
  color: $mono1;
  background-color: transparent;
  border: solid $mono1;
  border-radius: 10px;
  margin: 15px;
  align-items: center;
  justify-content: center;
}
nuxt-link,
a {
  color: $mono1;
}
nuxt-link:hover,
a:hover,
.go-back-button:hover {
  text-decoration: none;
  color: $mono3;
  background-color: $mono1;
}
</style>