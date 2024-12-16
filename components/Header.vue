<template>
  <nav>
    <div class="navbar">
      <!-- Logo -->
      <div class="navbar__logo">
        <a href="/">
          <img src="@/assets/images/logo.png" alt="logo_img" />
        </a>
      </div>

      <!-- Inline menu for desktop & burger menu for mobile -->
      <div class="navbar__menu">
        <Menu />
        <!-- Login and Signup buttons -->
        <div class="login-signup__buttons">
          <a href="/" class="login__buttons">LOGIN</a>
          <a href="/" class="signup__buttons">SIGN UP</a>
        </div>
      </div>
    </div>
  </nav>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Menu from "./Menu.vue";

export default defineComponent({
  name: "Header",
  components: {
    Menu,
  },
});
</script>

<style scoped>
.navbar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  position: absolute;
  padding: 2.7rem 2rem;
  left: 0;
  right: 0;
  top: 0;
  z-index: 9999;
}

.navbar__logo img {
  width: 100%;
  height: 100%;
}

.navbar__menu {
  display: flex;
  align-items: center;
  justify-content: flex-start;
  width: 100%;
  gap: 1em;
}

.login-signup__buttons {
  display: flex;
  gap: 10px;
  align-items: center;
}

.login-signup__buttons > a {
  text-decoration: none;
  font-weight: 500;
  font-size: 0.8rem;
  padding: 0.5rem 1rem;
  border-radius: 0.3rem;
  transition: all 0.3s;
}

.login__buttons {
  background-color: #42454a;
  border: 2px solid #42454a;
  color: #fff;
}

.signup__buttons {
  border: 2px solid #043f55;
  color: #043f55;
}

/* Desktop styles */
@media (min-width: 992px) {
  .navbar__menu {
    justify-content: flex-end;
  }

  .login-signup__buttons {
    gap: 20px; /* More spacing for desktop */
  }
}

/* Mobile styles */
@media (max-width: 991px) {
  .navbar__menu {
    flex-direction: row-reverse; /* Reverse order: login/signup first, menu last */
  }

  .login-signup__buttons {
    gap: 10px;
  }
}
</style>
