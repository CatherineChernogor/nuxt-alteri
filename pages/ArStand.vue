<template>
  <div>
    <client-only>
      <nuxt-link :to="'/'" exact>GO BACK</nuxt-link>
      <threejs-component />
      
    </client-only>
  </div>
</template>
<script>

export default {
  layout: "empty",
  components: {
    ThreejsComponent: process.browser
      ? () => import("../components/ArStand3D.vue")
      : null,
  },
};
</script>