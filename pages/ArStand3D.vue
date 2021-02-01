<template>
  <div>
    <client-only>
      <nuxt-link :to="'/'" exact class="go-back-button highlight" >GO BACK</nuxt-link>
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
      fov: 50,
      near: 0.1,
      far: 10000,
      positionA: 3000,
      positionB: 2000,
      positionC: 3000,
    },
    light: {
      skyColor: 0x989fa3,
      groundColor: 0x36322d,
      intensity: 1.5,
    },
    grid: {
      size: 10000,
      divisions: 100,
      colorCenterLine: 0xff0000,
      colorGrid: 0xffffff,
    },
    modelPath: "model_stand/stand_light.gltf",
    componentKey: 0,
  }),

  components: {
    Model: process.browser ? () => import("../components/Model.vue") : null,
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