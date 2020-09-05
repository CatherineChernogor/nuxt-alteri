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
        <ul class="prg">
          <li class="star">Инженерное мышление</li>
          <li class="star">Командная работа</li>
        </ul>
      </div>

      <div class="prg2 img-props prg">
        <img src="../assets/png/ar-land.png" class="d-block w-100" alt="арляндия" />
      </div>
    </div>

    <div class="item item2">
      <div class="highlight clr-green2 prg2 prg">На кого рассчитан проект</div>

      <div class="prg2">
        <div class="big-normal-text clr-green1 prg4 prg">Режим Соревнования</div>
        <div class="prg">Участники делятся на две-три команды. У каждой команды есть свое игровое поле. За четыре часа комагдам нужно спроектировать городскую среду, основываясь на предпочтениях граждан. Важно отметить, что горожане могут сами выбирать в каком городе им находится и всегда могут переехать в город противника. Побеждает команда с наибольшими показателями счастья и численности города.</div>
      </div>

      <div>
        <div class="big-normal-text clr-green1 prg3 prg">Образовательный Режим</div>

        <div
          class="prg4 prg"
        >AR-Ляндия - это еще и инженерный тренажер включающий в себя три образовательных курса:</div>

        <ul class="prg3 prg">
          <li class="star">Урбанистика</li>
          <li class="star">Анализ данных</li>
          <li class="star">3D-проектирование</li>
        </ul>

        <div class="prg">Курсы делять по степени сложности и позволяют подключать детей от 5го до 11го классов.</div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "/css/vars";

.wrapper {
  display: grid;
  grid-template-columns: repeat(2, 6fr);
  grid-gap: 20px;
  align-items: center;
  @include inherit;
    align-items: center;
}

.img-props {
  padding: 0 3rem;
}
/*
.star {
  content: url("../assets/svg/star-green.svg");
  height: 4em;
  width: 4em;
}*/
</style>