<template>
  <div>
    <client-only>
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