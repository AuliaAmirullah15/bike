<template>
  <div class="container">
    <input id="click" name="exit" type="checkbox" @click="menuToggle" />
    <label for="click"><span class="burger"></span></label>

    <div class="fullscreen-menu" v-if="menuOpened" @click="closeMenu">
      <ul class="menu-list">
        <li><a href="#section1">Home</a></li>
        <li><a href="#section2">About</a></li>
        <li><a href="#section3">Services</a></li>
        <li><a href="#section4">Contact</a></li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "Menu",
  data() {
    return {
      menuOpened: false,
    };
  },
  computed: {
    menuTitle() {
      return this.menuOpened ? "CLOSE" : "MENU";
    },
  },
  methods: {
    menuToggle() {
      this.menuOpened = !this.menuOpened;
    },
    closeMenu() {
      this.menuOpened = false;
    },
  },
};
</script>

<style scoped>
.container {
  position: absolute;
  top: 50%;
  margin: -20px 0 0 -65px;
  height: 40px;
}

.container input {
  display: none;
}

.container label {
  position: relative;
  width: 70px;
  height: 30px;
  top: 6px;
  display: block;
  cursor: pointer;
  background: transparent;
}

.container label:after,
.container input:checked + label:after {
  content: "";
  position: absolute;
  top: 50%;
  margin-top: -2px;
  width: 30px;
  height: 2px;
  border-radius: 2px;
  background: #42454a;
}

.container label .burger:before {
  content: "";
  position: absolute;
  top: 6px;
  width: 10px;
  left: 20px;
  height: 2px;
  border-radius: 2px;
  background: #42454a;
}

.container label .burger:after {
  content: "";
  position: absolute;
  bottom: 8px;
  width: 30px;
  height: 2px;
  border-radius: 2px;
  background: #42454a;
}

.fullscreen-menu {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.9);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 1000;
}

.menu-list {
  list-style: none;
  padding: 0;
  text-align: center;
}

.menu-list li {
  margin: 20px 0;
}

.menu-list li a {
  text-decoration: none;
  font-size: 24px;
  color: #ffffff;
  transition: color 0.3s ease;
}

.menu-list li a:hover {
  color: #ff6f61;
}
</style>
