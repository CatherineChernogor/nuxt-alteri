<template>
  <div class="idea">
    <div class="heading button-head">
      <span class>НАША ИДЕОЛОГИЯ</span>
    </div>

    <div class="slider">
      <div class="quote clr-mono1"><span class="bclr-mono3 quote-border">new experience</span></div>
      <div class="quote clr-mono1"><span class="bclr-mono3 quote-border">breaking boundaries between the world</span></div>
      <div class="quote clr-mono1"><span class="bclr-mono3 quote-border">стремимся к невозможному</span></div>
    </div>bclr-mono3
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
    width: 100%;
    height: 400px;
    .quote-border {
      padding: 3px 5px;
    }
  }
}

@keyframes
</style>