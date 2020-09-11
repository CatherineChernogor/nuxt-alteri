<template>
  <div class="clr-mono1 medium-normal-text wrapper">
    <div class="item item1">
      <div class="quote clr-red2 prg2 prg">Виртуализация игр</div>

      <div
        class="prg4 prg"
      >Tехнология, которая позволяет соединять игроков из разных точек вселенной. Вы можете купить любую настольную игру и, подключив ar-приложение, видеть ходы противника. Помимо этого - использование AR позволяет добавить в игру разные графические эффекты.</div>

      <div class="prg">
        <img src="../static/png/virtual.png" class="d-block w-100" alt="виртуал" />
      </div>
    </div>

    <div class="item item2">
      <div class="prg1">
        <div
          class="prg2 prg"
        >Одной из частей современной развлекательной культуры являются настольные игры. Они являются отличным средством для совместного времяпровождения с друзьями и отличной альтернативой хождению в кино или боулинг.</div>
        <div
          class="prg"
        >Проблемой настольных игр является, что для многих игр минимальное количество игроков от 4 до 8. И уж тем более в настолку нельзя поиграть одному.</div>
      </div>

      <div>
        <div class="highlight clr-red2 prg4 prg">На кого рассчитан проект</div>
        <div
          class="prg2 prg"
        >Если вы разработчик настольной игры или распространитель, вы можете заказать у нас услугу "виртуализация игры". Таким образом ваши игроки, смогут купить игру даже в случае, если у них нет полной команды!</div>
        <div
          class="prg"
        >Все что нужно надеть очки виртуальной реальности, к примеру гугл кардборд и наслаждаться игрой с виртуальным противником.</div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "/assets/css/vars";

.wrapper {
  display: grid;
  grid-template-columns: repeat(2, 6fr);
  grid-gap: 20px;
  @include inherit;
  align-items: center;
}
.item {
  text-align: left;
}
/*
.star {
  content: url("../assets/svg/star-green.svg");
  height: 4em;
  width: 4em;
}*/
</style>