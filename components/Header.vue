<template>
  <header class="bclr-mono3">
    <img class="logo" src="../static/svg/logo.svg" alt="LOGO" />

    <nav>
      <ul class="heading">
        <li class="nav-item">
          <div class="nav-link clr-mono1" v-on:click="setActive('aboutus')">О НАС</div>
        </li>
        <li class="nav-item">
          <div
            class="nav-link dropdown-toggle clr-mono1"
            data-toggle="dropdown"
            role="button"
            aria-haspopup="true"
            aria-expanded="false"
          >ПРОДУКТЫ</div>
          <div class="dropdown-menu medium-normal-text">
            <a class="dropdown-item" v-on:click="setActive('arstand')">AR-Stand</a>
            <a class="dropdown-item" v-on:click="setActive('arland')">AR-Land</a>
            <div role="separator" class="dropdown-divider"></div>
            <a class="dropdown-item" v-on:click="setActive('virtual')">Виртуализация Игр</a>
          </div>
        </li>
        <li class="nav-item">
          <div class="nav-link clr-mono1" v-on:click="setActive('contacts')">КОНТАКТЫ</div>
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

        if (message === "contacts" && i === 0)
          item.className = "carousel-item active";
      });
    },
  },
};
</script>

<style lang="scss">
@import "/assets/css/vars";
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
.nav-link {
  @include inherit;
  @include flexible;
  
}

ul {
  margin: 0;
}
.nav-item {
  display: inline-block;
  align-items: center;
  max-height: inherit;
  height: 100%;
}

nav > ul {
  display: flex;
  flex-direction: row;
}

nav,
ul {
  @include inherit;
  right: 0;
}

$line-height: 3px;

li.nav-item {
  display: inline-block;
  position: relative;
  text-decoration: none;
}
li.nav-item:before {
  display: block;
  position: absolute;
  content: "";
  height: $line-height;
  width: 0;
  background: $mono1;
  transition: width 0.3s ease-in-out, left 0.3s ease-in-out;
  left: 50%;
  bottom: 0;
}
li.nav-item:after {
  display: block;
  position: absolute;
  content: "";
  height: $line-height;
  width: 0;
  background-color: $mono1;
  transition: width 0.3s ease-in-out;
  left: 50%;
  bottom: 0;
}

li.nav-item:hover:before {
  width: 50%;
  left: 0;
}
li.nav-item:hover:after {
  width: 50%;
}
</style>