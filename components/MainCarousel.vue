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
      <span class="carousel-control-prev-icon" aria-hidden="true">
        <svg
          width="45"
          height="80"
          viewBox="0 0 45 80"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M44.2917 4.84484L9.37027 39.6458L9.01488 40L9.37027 40.3542L44.2917 75.1552L40.1384 79.2941L0.70833 40L40.1384 0.705888L44.2917 4.84484Z"
            stroke="#E5E5E5"
          />
        </svg>
      </span>
      <span class="sr-only">Previous</span>
    </a>
    <a
      class="carousel-control-next"
      href="#carouselExampleIndicators"
      role="button"
      data-slide="next"
    >
      <span class="carousel-control-next-icon" aria-hidden="true">
        <svg
          width="45"
          height="80"
          viewBox="0 0 45 80"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M0.708332 4.84484L35.6297 39.6458L35.9851 40L35.6297 40.3542L0.708332 75.1552L4.86161 79.2941L44.2917 40L4.86161 0.705888L0.708332 4.84484Z"
            stroke="#E5E5E5"
          />
        </svg>
      </span>
      <span class="sr-only">Next</span>
    </a>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
@import "/css/vars";

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
</style>