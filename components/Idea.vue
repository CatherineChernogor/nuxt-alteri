<template>
  <div class="idea">
    <div class="heading button-head">
      <span class>НАША ИДЕОЛОГИЯ</span>
    </div>

    <div class="slider">
      <no-ssr>
        <!-- important to add no-ssr

        <carousel :items=1 :loop=true :center=true :autoplay=true>

            <div class="quote quote-border">new experiense</div>
            <div class="quote quote-border">breaking button</div>
            <div class="quote quote-border">from rods to stars</div>
        </carousel>-->
      </no-ssr>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
@import "/css/vars";
.idea {
  .button-head.heading {
    padding: 20px 30px;
    span {
      border: solid $mono3 2px;
      padding: 10px 20px;
    }
  }
  .slider {
  }
}
</style>