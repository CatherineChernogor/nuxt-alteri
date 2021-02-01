<template>
  <div class="wrapper0">
    <div class="item item1">
      <div class="quote clr-purple2 prg2 prg">
        <span class="glit">О НАС</span> О НАС
      </div>
      <div class="medium-normal-text clr-mono1 prg pad">
        Мы команда энтузиастов из Сибири. Цель нашей
        компании - ломать границы между мирами,
        разрабатывая новые подходы, на базе технологий
        смешанной и дополненной реальности.
      </div>
      <div class="wrap-contact">
      <contacts-inline />
      </div>
    </div>
    <div class="item item2">
      <Layout />
    </div>
  </div>
</template>

<script>
import ContactsInline from './ContactsInline.vue';
export default {
  components: { ContactsInline },};
</script>

<style lang="scss" scoped>
@import "/assets/css/vars";

.wrapper0 {
  @include inherit;
  @include gridable;
  grid-template-columns: repeat(2, 1fr);
}
.item1 {
  padding-bottom: 200px;
}
.pad {
  padding-right: 30px;
}
.item2 {
  @include gridable;
  @include inherit;
  grid-auto-columns: 1;
  grid-auto-rows: 2;
}
.wrap-contact{
  padding: 50px 50px 0px 20px;
}
</style>