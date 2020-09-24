<template>
  <div class="layout" @mouseleave="leaveLayout" @mouseenter="enterLayout">
    <div class="premask">
      <Idea />
      <ContactsInline />
    </div>
    <div class="mask">
      <Team />
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    fadeIn(el, speed) {
      el.style.opacity = 0;
      var interval = setInterval(() => {
        el.style.opacity = parseFloat(el.style.opacity) + 0.01;
        if (el.style.opacity == 1.0) {
          clearInterval(interval);
        }
      }, speed / 10);
    },
    fadeOut: (el, speed) => {
      el.style.opacity = 1.0;
      var interval = setInterval(() => {
        el.style.opacity = parseFloat(el.style.opacity) - 0.01;
        if (el.style.opacity == 0) {
          clearInterval(interval);
        }
      }, speed / 10);
    },
    leaveLayout() {
      console.log("leave");
      let premask = document.querySelector(".premask");
      this.fadeIn(premask, 100);
    },
    enterLayout() {
      console.log("enter");
      let premask = document.querySelector(".premask");

      this.fadeOut(premask, 200);
    },
  },
};
</script>

<style lang="scss" scoped>
@import "/assets/css/vars";

.bg,
.premask,
.mask {
  @include inherit;
  @include flexible;
  flex-direction: column;
  width: 100%;
}
.layout {
  @include inherit;
  @include gridable;
  flex-direction: column;
  width: 100%;
}

.premask {
  grid-row: 1/2;
  grid-column: 1/2;
  background-image: url("../static/png/layouts/layout1.png");
  background-size: cover;
  background-repeat: no-repeat;
  z-index: 1;
}
.mask {
  grid-row: 1/2;
  grid-column: 1/2;
  margin-bottom: auto;
  margin-top: auto;
  z-index: 0;
}
</style>