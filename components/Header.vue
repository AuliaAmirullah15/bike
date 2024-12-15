<template>
  <nav>
    <div class="navbar">
      <div class="navbar__logo">
        <a href="/">
          <img src="@/assets/images/logo.png" alt="logo_img" />
        </a>
      </div>
      <div class="navbar__menu">
        <div class="login-signup__buttons">
          <a href="/" class="login__buttons">LOGIN</a>
          <a href="/" class="signup__buttons">SIGN UP</a>
        </div>
        <div><Menu></Menu></div>
      </div>
    </div>
  </nav>
</template>

<script>
import Menu from "./Menu.vue";

export default {
  name: "Header",
  components: {
    Menu,
  },
};
</script>

<style scoped>
.navbar {
  display: flex;
  height: auto;
  align-items: center;
  background-color: initial;
  justify-content: space-between;
  left: 0;
  margin: 0 auto;
  position: absolute;
  padding: 2.7rem 2rem;
  right: 0;
  top: 0;
  z-index: 9999;
}

.navbar__logo img {
  width: 100%;
  height: 100%;
}
.login-signup__buttons {
  display: flex;
  margin-right: 60pt;
  justify-content: space-between;
}

.login-signup__buttons > a {
  margin: 0 4px;
  align-items: center;
  display: flex;
  font-weight: 500;
  text-decoration: none;
}
.navbar__menu {
  display: flex;
}

.login__buttons {
  background-color: #42454a;
  border: 2px solid #42454a;
  color: #fff;
  border-radius: 0.3rem;
  padding: 0.5rem 1rem;
  transition: all 0.3s;
}

.signup__buttons {
  border: 2px solid #043f55;
  color: #043f55;
  border-radius: 0.3rem;
  padding: 0.5rem 1rem;
  transition: all 0.3s;
}

.login-signup__buttons > a {
  font-size: 0.8rem;
}

@media (max-width: 992px) {
  .navbar__logo {
    width: 34pt;
  }
}
</style>
