<template>
  <div class="clr-mono1 medium-normal-text wrapper">
    <div class="item item1">
      <div class="quote clr-green2 prg2 prg">AR-Ляндия</div>

      <div class="prg2 prg">Это командная игра, которая может быть выстроена в нескольких режимах.</div>

      <div
        class="prg2 prg"
      >Это детская стратегическая настольная игра. Детям предлагается выступить в роли урбанистов и спроектировать городскую среду. В ходе игры они могут анализировать предпочтения горожан, их поведение, и на основе этого делать предположение о том как следует застроить город.</div>

      <div class="prg2">
        <div class="highlight clr-green2 prg4 prg">Какие навыки будут развиты</div>
        <ul class="prg star-list green-star">
          <li>Инженерное мышление</li>
          <li>Командная работа</li>
        </ul>
      </div>

      <div class="prg2 img-props prg">
        <nuxt-link :to="'/ArLand'">
          <div class="img-row">
            <img src="../static/png/ar-land.png" class="d-block stand" alt="арляндия" />

            <img
              src="../static/svg/flying_arrow-green.svg"
              class="d-block arrow bounce-2"
              alt="arrow"
            />
          </div>
        </nuxt-link>
      </div>
    </div>

    <div class="item item2">
      <div class="highlight clr-green2 prg2 prg">На кого рассчитан проект</div>

      <div class="prg2">
        <div class="big-normal-text clr-green1 prg4 prg">Режим Соревнования</div>
        <div
          class="prg"
        >Участники делятся на две-три команды. У каждой команды есть свое игровое поле. За четыре часа комагдам нужно спроектировать городскую среду, основываясь на предпочтениях граждан. Важно отметить, что горожане могут сами выбирать в каком городе им находится и всегда могут переехать в город противника. Побеждает команда с наибольшими показателями счастья и численности города.</div>
      </div>

      <div>
        <div class="big-normal-text clr-green1 prg3 prg">Образовательный Режим</div>

        <div
          class="prg4 prg"
        >AR-Ляндия - это еще и инженерный тренажер включающий в себя три образовательных курса:</div>

        <ul class="prg3 prg star-list green-star">
          <li>Урбанистика</li>
          <li>Анализ данных</li>
          <li>3D-проектирование</li>
        </ul>

        <div
          class="prg"
        >Курсы делять по степени сложности и позволяют подключать детей от 5го до 11го классов.</div>
        <br />
        <br />
        <br />
        <br />
        <br />
        <br />
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "/assets/css/vars";

.wrapper {
  display: grid;
  grid-template-columns: repeat(2, 6fr);
  grid-gap: 30px;
  @include inherit;
  align-items: start;
  margin: 20px 0;
}
.item1,
.item2 {
  padding-top: 5rem;
}
.img-props {
  /*margin: 0 -3rem;*/
  margin: 0 auto;
}
.img-row {
  display: flex;
  flex-direction: row;
}
.stand {
  padding: 0 1rem;
  max-height: 30vh;
  height: auto;
  width: auto;
}
.arrow {
  height: $flying-arrow-size;
  width: $flying-arrow-size;
  padding-right: $flying-arrow-size/2;
  margin: 0 auto;
  margin-bottom: 60% ;
  transform: rotate(90deg);

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
    transform: translateX(-20px);
  }
  50% {
    transform: translateX(-70px);
  }
  100% {
    transform: translateX(-20px);
  }
}
</style>