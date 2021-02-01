<template>
  <div class="wrapper0">
    <div class="item">
      <div class="quote clr-purple2 prg2 prg align">
        <span class="glit"
          >КОМАНДА</span
        >
        КОМАНДА
      </div>
      <Team />
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
@import "/assets/css/vars";

.wrapper0 {
  @include inherit;
  @include gridable;
  grid-template-columns: repeat(1, 1fr);
}
.align{
  justify-content: center;
  text-align: center;
}
// .item1 {
//   padding-bottom: 200px;
// }
// .pad {
//   padding-right: 30px;
// }
// .item2 {
//   @include gridable;
//   @include inherit;
//   grid-auto-columns: 1;
//   grid-auto-rows: 2;
// }
</style>