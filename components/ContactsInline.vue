<template>
  <div class="contacts clr-mono3">
    <div class="row">
      <div class="header tiny-bold-text"><strong>Найдите нас</strong></div>

      <div class="line">
        <div class="img-vk"></div>
        <div class="caption tiny-semibold-text">vk.com / alteri_lab</div>
      </div>
      <div class="line">
        <div class="img-inst"></div>
        <div class="caption tiny-semibold-text">instagram.com / alteri_lab</div>
      </div>
    </div>
    <div class="row">
      <div class="header tiny-bold-text">Напишите нам</div>

      <div class="line">
        <div class="img-mail"></div>
        <div class="caption tiny-semibold-text">altruist@alteri-lab.ru</div>
      </div>
      <div class="line">
        <div class="img-web"></div>
        <div class="caption tiny-semibold-text">www.alteri-lab.ru</div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "/assets/css/vars";

.contacts {
  // @include flexible;
  // margin-top: 300px;
  padding-left: 20%;
  justify-content: start;
  flex-direction: column;
  color: $mono1;

  border: solid $mono1 2px;
  border-radius: 50px;
}
.row {
  flex-direction: column;
  justify-content: flex-end;
  text-align: left;
  margin: 30px 0px;
  .header {
    padding-bottom: 10px;
  }
  .line {
    @include flexible;
    flex-direction: row;
    justify-content: flex-start;
    padding: 2px;
  }
}

.img-vk,
.img-inst,
.img-web,
.img-mail {
  background-repeat: no-repeat;
  background-size: cover;
  min-width: 10px;
  min-height: 10px;
  width: 20px;
  height: 20px;
  margin-right: 10px;
  
}
.img-vk {
  background-image: url("../static/svg/vk.svg");
}
.img-inst {
  background-image: url("../static/svg/instagram.svg");
}
.img-web {
  background-image: url("../static/svg/web.svg");
}
.img-mail {
  background-image: url("../static/svg/mail.svg");
}
</style>