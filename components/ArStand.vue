<template>
  <div class="clr-mono1 medium-normal-text wrapper">
    <div class="item item1">
      <div class="prg1">
        <div class="quote clr-blue2 prg2 prg grit-mono1">AR-Stand</div>
        <div
          class="prg"
        >Конструктор для создания сцен гибридной реальности, где физический и цифровой объекты существуют и взаимодействуют в реальном времени.</div>
      </div>

      <div
        class="prg1 prg"
      >Элементами управляющего интерфейса стенда являются кубики, комбинация которых на стенде сопровождается звуковым или графическим эффектом.</div>

      <div class="prg1">
        <div class="highlight clr-blue2 prg4 prg">Какие навыки будут развиты</div>
        <ul class="prg">
          <li class="star">Инженерное мышление</li>
          <li class="star">Командная работа</li>
        </ul>
      </div>
    </div>

    <div class="item item2 prg">
      <img src="../assets/png/ar-stand.png" class="d-block w-100" alt="стенд" />
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
        <ul class="prg">
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
@import "/css/vars";

.wrapper {
  display: grid;
  grid-template-columns: 4fr 3fr 5fr;
  /*grid-gap: 20px;*/
  @include inherit;
    align-items: center;
}
.item {
  text-align: left;
}
/*
.star {
  content: url("../assets/svg/star-blue.svg");
  height: 4em;
  width: 4em;
}*/
</style>