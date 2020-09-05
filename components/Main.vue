<template>
  <div class="wrapper0">
    <div class="item item1">
      <div class="quote clr-purple2 prg2 prg">О НАС</div>
      <div class="medium-normal-text clr-mono1 prg">
        Мы команда энтузиастов из Сибири. Цель нашей
        компании - ломать границы между мирами,
        разрабатывая новые подходы, на базе технологий
        смешанной и дополненной реальности.
      </div>
    </div>
    <div class="item item2 bg">
      <div class="mask humans">
        <Team />
      </div>
      <div class="premask">
        <Idea />
        <ContactsInline />
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
  grid-template-columns: repeat(2, 1fr);
}
.item1{
  padding-bottom: 200px;
}

.item2 {
  @include gridable;
  @include inherit;
  grid-auto-columns: 1;
  grid-auto-rows: 2;
}
.bg {
  background-image: url("../assets/png/layouts/layout2.png");
  background-size: cover;
  background-repeat: no-repeat;
  
  &:hover {
    animation: grow 3000ms ease;
  }
}
.premask {
  grid-row: 1/2;
  grid-column: 1/2;
}

.mask {
  @include inherit;
  display: flex;
  align-items: center;
  grid-row: 1/2;
  grid-column: 1/2;
  margin-bottom: auto;
  margin-top: auto;
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