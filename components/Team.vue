<template>
  <div class="humans small-normal-text">
    <div class="line line1">
      <div class="human human1">
        <div class="human-img human-img1"></div>
        <div class="name">Воловикова Зоя</div>
        <div class="separator"></div>
        <div class="caption">Президент, специалист по компьютерному зрению</div>
      </div>

      <div class="human human2">
        <div class="human-img human-img2"></div>
        <div class="name">Веснин Артем</div>
        <div class="separator"></div>
        <div class="caption">R&amp;D</div>
      </div>

      <div class="human human3">
        <div class="human-img human-img3"></div>
        <div class="name">Абдулов Александр</div>
        <div class="separator"></div>
        <div class="caption">Главный программный разработчик</div>
      </div>

      <div class="human human4">
        <div class="human-img human-img4"></div>
        <div class="name">Пинкин Андрей</div>
        <div class="separator"></div>
        <div class="caption">Игротехник, игровой дизайнер</div>
      </div>
    </div>
    <div class="line line2">
      <div class="human human5">
        <div class="human-img human-img5"></div>
        <div class="name">Быков Алексей</div>
        <div class="separator"></div>
        <div class="caption">Специалист по машинному обучению и анализу данных</div>
      </div>

      <div class="human human6">
        <div class="human-img human-img6"></div>
        <div class="name">Карамышев Артем</div>
        <div class="separator"></div>
        <div class="caption">Специалист по компьютерному зрению, разработчик Unity</div>
      </div>

      <div class="human human7">
        <div class="human-img human-img7"></div>
        <div class="name">Черногор Екатерина</div>
        <div class="separator"></div>
        <div class="caption">Web-developer, разработчик Unity</div>
      </div>
    </div>
  </div>
</template>


<style lang="scss" scoped>
@import "/assets/css/vars";

$block-width: 120px;

.humans {
  @include flexible;
  flex-direction: column;
  border-left: solid $mono1 2px;
}
.human {
  @include flexible;
  color: $mono1;
  flex-direction: column;
  max-width: mimimax($block-width * 1.75, auto);
}

.line {
  @include flexible;
  flex-direction: row;
  padding-bottom: 30px;
  align-items: flex-start;
}

.human-img {
  height: $block-width;
  width: $block-width;
  background-size: cover;
  border-radius: 50%;
}

.separator {
  height: 3px;
  width: $block-width * 0.75;
  background-color: $mono1;
}

.name {
  padding: 15px 0;
  width: $block-width * 1.5;
}

.caption {
  padding: 15px 10px;
  width: $block-width * 1.5;
}

.human-img1 {
  background-image: url("../static/png/humans/h1.webp");
}

.human-img2 {
  background-image: url("../static/png/humans/h2.webp");
}

.human-img3 {
  background-image: url("../static/png/humans/h3.webp");
}

.human-img4 {
  background-image: url("../static/png/humans/h4.webp");
}

.human-img5 {
  background-image: url("../static/png/humans/h5.webp");
}

.human-img6 {
  background-image: url("../static/png/humans/h6.webp");
}

.human-img7 {
  background-image: url("../static/png/humans/human-7.png");
}
</style>