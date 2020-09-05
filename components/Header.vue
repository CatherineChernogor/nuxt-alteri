<template>
  <header class="bclr-mono3">
    <img class="logo" src="../assets/svg/logo.svg" alt="LOGO" />

    <nav>
      <ul class="heading">
        <li class="nav-item">
          <span class="nav-link clr-mono1" v-on:click="setActive('aboutus')">О НАС</span>
        </li>
        <li class="nav-item">
          <span
            class="nav-link dropdown-toggle clr-mono1"
            data-toggle="dropdown"
            role="button"
            aria-haspopup="true"
            aria-expanded="false"
          >ПРОДУКТЫ</span>
          <div class="dropdown-menu medium-normal-text">
            <a class="dropdown-item" v-on:click="setActive('arstand')">AR-Stand</a>
            <a class="dropdown-item" v-on:click="setActive('arland')">AR-Land</a>
            <div role="separator" class="dropdown-divider"></div>
            <a class="dropdown-item" v-on:click="setActive('virtual')">Виртуализация Игр</a>
          </div>
        </li>
        <li class="nav-item">
          <span class="nav-link clr-mono1" v-on:click="setActive('contacts')">КОНТАКТЫ</span>
        </li>
      </ul>
    </nav>
  </header>
</template>

<script>
export default {
  methods: {
    setActive: function (message) {
      let list = ["aboutus", "arstand", "arland", "virtual", "contacts"];

      document.querySelectorAll(".carousel-item").forEach(function (item, i) {
        item.className =
          i === list.indexOf(message)
            ? "carousel-item active"
            : "carousel-item";


        if (message === 'contacts' && i === 0)
          item.className = "carousel-item active";
      });
    },
  },
};
</script>

<style>
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
.nav-link:hover,
.dropdown-item:hover {
  cursor: pointer;
  z-index: 99999;
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