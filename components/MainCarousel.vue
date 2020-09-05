<template>
  <div id="carouselExampleIndicators" class="carousel slide" data-ride="carousel">
    <ol class="carousel-indicators">
      <li data-target="#carouselExampleIndicators" data-slide-to="0" class="active"></li>
      <li data-target="#carouselExampleIndicators" data-slide-to="1"></li>
      <li data-target="#carouselExampleIndicators" data-slide-to="2"></li>
      <li data-target="#carouselExampleIndicators" data-slide-to="3"></li>
    </ol>
    <div class="carousel-inner">
      <div class="carousel-item active">

        <Main />
      </div>

      <div class="carousel-item">
        <ArStand />
      </div>
      
      <div class="carousel-item">
        <ArLand />
      </div>
      <div class="carousel-item">
        <Virtual />
      </div>
    </div>
    <a
      class="carousel-control-prev"
      href="#carouselExampleIndicators"
      role="button"
      data-slide="prev"
    >
      <span class="carousel-control-prev-icon" aria-hidden="true"></span>
      <span class="sr-only">Previous</span>
    </a>
    <a
      class="carousel-control-next"
      href="#carouselExampleIndicators"
      role="button"
      data-slide="next"
    >
      <span class="carousel-control-next-icon" aria-hidden="true"></span>
      <span class="sr-only">Next</span>
    </a>
  </div>
</template>

<script>
export default {

};
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