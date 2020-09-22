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
      <div class="carousel-item ">
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
export default {};
</script>

<style lang="scss" scoped>
@import "/assets/css/vars";

.carousel {
  @include inherit;
  margin-top: 5rem;
}
.carousel-control-prev,
.carousel-control-next {
  width: auto;
  min-width: 20px;

  padding: 5px;
}
.carousel-inner {
  position: inherit;
  align-items: center;
  min-height: inherit;
  height: inherit;
  max-width: 1000px;
}
.carousel-item {
  align-items: center;
  @include inherit;
}

.carousel-control-prev-icon,
.carousel-control-next-icon {
  width: 40px;
  height: 40px;
  background-image: unset;
}
.carousel-control-next-icon {
  background-image: url("../static/svg/arrow-next.svg");
}
.carousel-control-next-icon:hover {
  background-image: url("../static/svg/arrow-next-hover.svg");
}
.carousel-control-prev-icon {
  background-image: url("../static/svg/arrow-prev.svg");
}
.carousel-control-prev-icon:hover {
  background-image: url("../static/svg/arrow-prev-hover.svg");
}


</style>