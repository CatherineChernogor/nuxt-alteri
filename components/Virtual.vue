<template>
  <div class="clr-mono1 medium-normal-text wrapper">
    <div class="item item1">
      <div class="quote clr-red2 prg2 prg">
        <span class="glit">Виртуализация игр</span>Виртуализация игр
      </div>

      <div
        class="prg4 prg"
      >Tехнология, которая позволяет соединять игроков из разных точек вселенной. Вы можете купить любую настольную игру и, подключив ar-приложение, видеть ходы противника. Помимо этого - использование AR позволяет добавить в игру разные графические эффекты.</div>

      <div class="prg">
        <img src="../static/png/virtual.png" class="d-block w-100" alt="виртуал" />
      </div>
    </div>

    <div class="item item2">
      <div class="prg1">
        <div class="prg2 prg">
          Одной из частей современной развлекательной культуры являются
          <span
            class="clr-red1"
          >настольные игры.</span>
          Они являются отличным средством для совместного времяпровождения с друзьями и отличной альтернативой хождению в кино или боулинг.
        </div>
        <div class="prg">
          <span class="clr-red1">Проблемой</span>
          настольных игр является, что для многих игр
          <span class="clr-red1">минимальное</span>
          количество игроков
          <span class="clr-red1">от 4 до 8.</span>
          И уж тем более в настолку
          <span class="clr-red1">нельзя</span>
          поиграть
          <span class="clr-red1">одному.</span>
        </div>
      </div>

      <div>
        <div class="highlight clr-red2 prg4 prg">На кого рассчитан проект</div>
        <div class="prg2 prg">
          Если вы
          <span class="clr-red1">разработчик</span>
          настольной игры или
          <span class="clr-red1">распространитель</span>
          распространитель, вы можете заказать у нас услугу "виртуализация игры". Таким образом ваши игроки, смогут купить игру даже в случае, если у них нет полной команды!
        </div>
        <div
          class="prg"
        >Все что нужно надеть очки виртуальной реальности, к примеру гугл кардборд и наслаждаться игрой с виртуальным противником.</div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "/assets/css/vars";
.big-Wrap {
  @include flexible;
  align-items: center;
}
.wrapper {
  display: grid;
  grid-template-columns: repeat(2, 6fr);
  grid-gap: 30px;
  @include inherit;
  align-items: start;
}
.item {
  text-align: left;
}
.item1,
.item2 {
  padding-top: 5rem;
}
</style>