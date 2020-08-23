<template>
  <div>
    <div id="carouselExampleIndicators" class="carousel slide" data-ride="carousel">
      <ol class="carousel-indicators">
        <li data-target="#carouselExampleIndicators" data-slide-to="0" class="active"></li>
        <li data-target="#carouselExampleIndicators" data-slide-to="1"></li>
        <li data-target="#carouselExampleIndicators" data-slide-to="2"></li>
        <li data-target="#carouselExampleIndicators" data-slide-to="3"></li>
      </ol>
      <div class="carousel-inner container">
        <div class="carousel-item active">
          <img src="../assets/png/layouts/layout4.png" class="d-block w-100" alt="about" />
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
  </div>
</template>

<script>
export default {};
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 93vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
    max-width: 1170px;
  min-width: auto;
}


.links {
  padding-top: 15px;
}

.carousel-item {
  margin: 0;
  padding: 0;
}
</style>
