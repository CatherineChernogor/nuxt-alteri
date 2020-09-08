<template>
  <div>
    <div class="heading button-head">
      <span class>НАША ИДЕОЛОГИЯ</span>
    </div>

    <div class="slider">
      <div class="mask clr-mono1">
        <ul>
          <li class="anim1">
            <div class="quote">
              <span class="bclr-mono3 quote-border slide1">new experience</span>
            </div>
          </li>
          <li class="anim2">
            <div class="quote">
              <span class="bclr-mono3 quote-border slide2">breaking boundaries between the world</span>
            </div>
          </li>
          <li class="anim3">
            <div class="quote">
              <span class="bclr-mono3 quote-border slide3">стремимся к невозможному</span>
            </div>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
@import "/css/vars";

.button-head.heading {
  padding: 20px 30px;
  span {
    border: solid $mono3 2px;
    padding: 10px 20px;
  }
}

.slider {
  overflow: visible;
  position: relative;
  width: 100%;
  height: 400px;
  .quote-border {
    padding: 3px 5px;
  }
}

.mask {
  overflow: hidden;
  height: 320px;
  @include flexible;
}

.slider ul {
  margin: 0;
  padding: 0;
  position: relative;
}

.slider li {
  position: inherit;
  top: -325px;
  list-style: none;
}

.slider li.anim1 {
  animation: cycle 30s linear infinite;
}

.slider li.anim2 {
  animation: cycle2 30s linear infinite;
}

.slider li.anim3 {
  animation: cycle3 30s linear infinite;
}



@keyframes cycle {
  0% {
    top: 0px;
  }
  4% {
    top: 0px;
  }
  16% {
    top: 0px;
    opacity: 1;
    z-index: 0;
  }
  20% {
    top: 325px;
    opacity: 0;
    z-index: 0;
  }
  21% {
    top: -325px;
    opacity: 0;
    z-index: -1;
  }
  50% {
    top: -325px;
    opacity: 0;
    z-index: -1;
  }
  92% {
    top: -325px;
    opacity: 0;
    z-index: 0;
  }
  96% {
    top: -325px;
    opacity: 0;
  }
  100% {
    top: 0px;
    opacity: 1;
  }
}

@keyframes cycle2 {
  0% {
    top: -325px;
    opacity: 0;
  }
  16% {
    top: -325px;
    opacity: 0;
  }
  20% {
    top: 0px;
    opacity: 1;
  }
  24% {
    top: 0px;
    opacity: 1;
  }
  36% {
    top: 0px;
    opacity: 1;
    z-index: 0;
  }
  40% {
    top: 325px;
    opacity: 0;
    z-index: 0;
  }
  41% {
    top: -325px;
    opacity: 0;
    z-index: -1;
  }
  100% {
    top: -325px;
    opacity: 0;
    z-index: -1;
  }
}

@keyframes cycle3 {
  0% {
    top: -325px;
    opacity: 0;
  }
  36% {
    top: -325px;
    opacity: 0;
  }
  40% {
    top: 0px;
    opacity: 1;
  }
  44% {
    top: 0px;
    opacity: 1;
  }
  56% {
    top: 0px;
    opacity: 1;
    z-index: 0;
  }
  60% {
    top: 325px;
    opacity: 0;
    z-index: 0;
  }
  61% {
    top: -325px;
    opacity: 0;
    z-index: -1;
  }
  100% {
    top: -325px;
    opacity: 0;
    z-index: -1;
  }
}
</style>