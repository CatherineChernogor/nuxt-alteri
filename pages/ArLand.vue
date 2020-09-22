<template>
  <div>
    <client-only>
      <nuxt-link :to="'/'" exact class="go-back-button highlight">GO BACK</nuxt-link>
      <threejs-component-arland />
    </client-only>
  </div>
</template>
<script>
export default {
  layout: "empty",
  components: {
    ThreejsComponentArland: process.browser
      ? () => import("../components/ArLand3D.vue")
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