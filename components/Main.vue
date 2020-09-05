<template>
  <div class="wrapper0">
    <div class="item item1">
      <div class="quote clr-purple2 prg2">О НАС</div>
      <div class="medium-normal-text clr-mono1">
        Мы команда энтузиастов из Сибири. Цель нашей
        компании - ломать границы между мирами,
        разрабатывая новые подходы, на базе технологий
        смешанной и дополненной реальности.
      </div>
    </div>
    <div class="item item2 bg">
      <Idea />
      <ContactsInline />
      <div class="mask humans">
        <Team />
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
@import "/css/vars";

.wrapper0 {
  align-items: center;
  @include inherit;
  @include gridable;
  grid-template-columns: 5fr 7fr;
}

.bg {
  background-image: url("../assets/png/layouts/layout2.png");
  background-size: cover;
  background-repeat: no-repeat;
  @include inherit;
  width: 100%;
  &:hover {
    animation: grow 3000ms ease;
  }
}
.mask {
  @include inherit;
  opacity: 0;
  &:hover {
    height: 100%;
    background-color: $mono3;
    animation: dark 60000ms ease;
  }
}
@keyframes grow {
  0% {
    transform: translateX(0);
    background-image: url("../assets/png/layouts/layout2.png");
  }
  50% {
    /*transform: scaleX(1.5);*/
    transform: translateX(200);
    background-image: url("../assets/png/layouts/layout1.png");
  }
  100% {
    /*transform: scaleX(1.5);*/
    transform: translateX(400);
    background-image: url("../assets/png/layouts/layout3.png");
  }
}

@keyframes dark {
  0% {
    opacity: 0;
  }
  100% {
    border-top: solid $mono1 3px;
    border-left: solid $mono1 2px;

    opacity: 100;
  }
}
</style>