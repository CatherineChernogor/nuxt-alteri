<!--
<template>
  <div class="header">
    <header>
      <div class="logo-alt"></div>

      <div class="placeholder-header">
        <div class="text-area-header">
          <span class="text-header">о нас</span>
        </div>
        <div class="text-area-header">
          <span class="text-header">продукты</span>
        </div>
        <div class="text-area-header">
          <span class="text-header">контакты</span>
        </div>
      </div>
    </header>
  </div>
</template>

<style>
@import url("https://fonts.googleapis.com/css2?family=Montserrat&display=swap");

.header {
  display: flex;
  flex-direction: row;
  background-color: black;
  justify-content: space-between;
  height: 100px;
}
.logo-alt {
  width: 295px;
  height: 57px;

  background: url("../assets/logo.png");
  background-origin: content-box;
}
.placeholder-header {
  display: flex;
  flex-direction: row;
}
.text-area-header {
  margin: 10px;
}
.text-header {
  font-family: "Montserrat", sans-serif;
  font-style: normal;
  font-weight: normal;
  font-size: 36px;
  line-height: 44px;
  /* identical to box height */

  letter-spacing: -0.07em;

  text-transform: uppercase;

  color: #c4c4c4;
}
</style>-->

<template>
  <div>
    <header>
      <nav id="navbar-example2" class="navbar navbar-light bg-light">
        <a class="navbar-brand" href="#">LOGO</a>
        <ul class="nav nav-pills">
          <li class="nav-item">
            <a class="nav-link" href="#aboutus">О НАС</a>
          </li>

          <li class="nav-item dropdown">
            <a
              class="nav-link dropdown-toggle"
              data-toggle="dropdown"
              href="#"
              role="button"
              aria-haspopup="true"
              aria-expanded="false"
            >ПРОДУКТЫ</a>
            <div class="dropdown-menu">
              <a class="dropdown-item" href="#arstand">AR-Stand</a>
              <a class="dropdown-item" href="#arland">AR-Land</a>
              <div role="separator" class="dropdown-divider"></div>
              <a class="dropdown-item" href="#virtual">Виртуализация Игр</a>
            </div>
          </li>

          <li class="nav-item">
            <a class="nav-link" href="#contacts">КОНТАКТЫ</a>
          </li>
        </ul>
      </nav>
    </header>
  </div>
</template>