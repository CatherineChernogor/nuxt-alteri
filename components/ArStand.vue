<template>
  <div class="clr-mono1 medium-normal-text wrapper">
    <div class="item item1">
      <div class="prg1">
        <div class="quote clr-blue2 prg2 prg grit-mono1">
          <span class="glit clr-blue2">AR-Stand</span> AR-Stand
        </div>
        <div class="prg">
          <span class="clr-blue2 glit">Конструктор</span>Конструктор для создания сцен гибрибной реальности, где физический и цифровой объекты существуют и взаимодействуют в реальном времени.
        </div>
      </div>

      <div
        class="prg1 prg"
      >Элементами управляющего интерфейса стенда являются кубики, комбинация которых на стенде сопровождается звуковым или графическим эффектом.</div>

      <div class="prg1">
        <div class="highlight clr-blue2 prg4 prg">Какие навыки будут развиты</div>
        <ul class="prg star-list blue-star">
          <li class="star">Инженерное мышление</li>
          <li class="star">Командная работа</li>
        </ul>
      </div>
    </div>

    <div class="item item2 prg">
      <nuxt-link :to="'/ArStand'">
        <div class="item2">
          <img src="../static/svg/flying_arrow-blue.svg" class="d-block arrow bounce-2" alt="arrow" />

          <img src="../static/png/ar-stand.png" class="d-block stand" alt="стенд" />
        </div>
      </nuxt-link>
    </div>

    <div class="item item3">
      <div class="prg2">
        <div class="highlight clr-blue2 prg4 prg">На кого рассчитан проект</div>
        <div class="prg">AR-Stand будет полезен в двух случаях:</div>
      </div>

      <div
        class="prg4 prg"
      >Для обучения маленьких детей (от 4х лет) алгоритмическому мышлению. Тактильность и специальное программное обеспечение снижают порог вхождение в обучение программированию. Таким образом набор курсов позволит плавно перейти из курса "малышковое программирования" в курс "разработчик игр".</div>

      <div
        class="prg2 prg"
      >Кроме того AR-Stand - это устройство, которое не только предоставляет ряд игр гибридной реальности.</div>

      <div class="prg2">
        <div
          class="prg4 prg"
        >Стенд включает в себя платформу для обучения технологиям заложенных в его основу:</div>
        <ul class="prg star-list blue-star">
          <li class="star">Компьютерное зрение</li>
          <li class="star">Проективная геометрия</li>
          <li class="star">Дополненная реальность</li>
          <li class="star">Машинное обучение</li>
        </ul>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "/assets/css/vars";

.wrapper {
  display: grid;
  grid-template-columns: 4fr 3fr 5fr;
  @include inherit;
  align-items: start;
}
.item1,
.item3 {
  padding-top: 5rem;
}
.item2 {
  display: flex;
  flex-direction: column;
  min-height: 500px;
  height: auto;
  width: 100%;
  align-items: center;
}
.stand {
  padding: 0 1rem;
  max-height: 65vh;
  height: auto;
  width: auto;
}
.arrow {
  height: $flying-arrow-size;
  width: $flying-arrow-size;
  padding-right: $flying-arrow-size/2;
  margin: 0 auto;

  align-self: flex-end;
  animation-duration: 2s;
  animation-iteration-count: infinite;
  transform-origin: bottom;
}
.bounce-2 {
  animation-name: bounce-2;
  animation-timing-function: ease;
}
@keyframes bounce-2 {
  0% {
    transform: translateY(20px);
  }
  50% {
    transform: translateY(-20px);
  }
  100% {
    transform: translateY(20px);
  }
}
</style>