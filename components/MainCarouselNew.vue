<template>
  <div>
    <no-ssr>
      <!-- important to add no-ssr-->

      <carousel :items="1" :loop="true" :center="true" :autoplay="true" :margin=200>
        <!--<Main />

        <ArStand />

        <ArLand />

        <Virtual />-->
        <img src="../assets/png/1.png">
        <img src="../assets/png/2.png">
        <img src="../assets/png/3.png">
        <img src="../assets/png/4.png">
      </carousel>
    </no-ssr>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
@import "/css/vars";

.carousel {
  @include inherit;
}
.carousel-control-prev,
.carousel-control-next {
  width: auto;
  min-width: 30px;
  padding: 10px;
}
.carousel-inner {
  position: inherit;
  align-items: center;
  min-height: inherit;
  height: inherit;
}
.carousel-item {
  align-items: center;
  @include inherit;
}
.carousel-control-prev-icon,
.carousel-control-next-icon {
}
</style>