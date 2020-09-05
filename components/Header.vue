<template>
  <header class="bclr-mono3">
    <img class="logo" src="../assets/svg/logo.svg" alt="LOGO" />

    <nav>
      <ul class="heading">
        <li class="nav-item">
          <nuxt-link class="nav-link clr-mono1" to="#aboutus">О НАС</nuxt-link>
        </li>
        <li class="nav-item">
          <a
            class="nav-link dropdown-toggle clr-mono1"
            data-toggle="dropdown"
            href="#"
            role="button"
            aria-haspopup="true"
            aria-expanded="false"
          >ПРОДУКТЫ</a>
          <div class="dropdown-menu medium-normal-text">
            <a class="dropdown-item" href="#arstand">AR-Stand</a>
            <a class="dropdown-item" href="#arland">AR-Land</a>
            <div role="separator" class="dropdown-divider"></div>
            <a class="dropdown-item" href="#virtual">Виртуализация Игр</a>
          </div>
        </li>
        <li class="nav-item">
          <a class="nav-link clr-mono1" href="#contacts">КОНТАКТЫ</a>
        </li>
      </ul>
    </nav>
  </header>
</template>
<style>
/*.head{
  display: inline ;
      text-align: justify;
    letter-spacing: 1px;
    height: 8em;
    padding: 2em 10%;

}
.navbar-size{
  position: fixed;
  max-height: 100px;
max-width: auto;
}
.nav-link:hover {
  text-decoration: underline;
  color: #e5e5e5;
}
*/
header {
  display: flex;
  top: 0;
  position: fixed;
  height: 5rem;

  justify-content: space-between;
  align-items: center;
  text-align: center;

  max-width: 100vw;
  width: -webkit-fill-available;
  min-width: auto;
}
.logo {
  height: auto;
  width: auto;
  max-height: 3rem;
  padding: 0 15px;
}
ul {
  margin: 0;
}
.nav-item {
  display: inline-block;
  vertical-align: middle;
}
nav > ul {
  display: flex;
  flex-direction: row;
}
</style>