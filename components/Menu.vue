<template>
  <div class="menu-wrapper">
    <!-- Input and label for mobile -->
    <input id="click" name="exit" type="checkbox" @click="menuToggle" />
    <label for="click"><span class="burger"></span></label>

    <!-- Fullscreen menu for mobile, inline menu for desktop -->
    <transition name="menu-slide">
      <div
        class="menu-list-wrapper"
        :class="{ 'menu-inline': isDesktop, 'fullscreen-menu': !isDesktop }"
        v-if="menuOpened || isDesktop"
        @click="handleMenuClick"
      >
        <ul class="menu-list">
          <li><a href="#section1">Home</a></li>
          <li><a href="#section2">About</a></li>
          <li><a href="#section3">Services</a></li>
          <li><a href="#section4">Contact</a></li>
        </ul>
      </div>
    </transition>
  </div>
</template>

<script lang="ts">
import { ref, onMounted, onBeforeUnmount } from "vue";

export default {
  name: "Menu",
  setup() {
    const menuOpened = ref(false);
    const isDesktop = ref(false);

    const menuToggle = (): void => {
      menuOpened.value = !menuOpened.value;
    };

    const closeMenu = (): void => {
      menuOpened.value = false;
    };

    const handleMenuClick = (): void => {
      if (!isDesktop.value) {
        closeMenu();
      }
    };

    const handleResize = (): void => {
      isDesktop.value = window.innerWidth >= 992;
      if (isDesktop.value) {
        menuOpened.value = false;
      }
    };

    onMounted(() => {
      handleResize();
      window.addEventListener("resize", handleResize);
    });

    onBeforeUnmount(() => {
      window.removeEventListener("resize", handleResize);
    });

    return {
      menuOpened,
      isDesktop,
      menuToggle,
      handleMenuClick,
    };
  },
};
</script>

<style lang="scss" scoped>
.menu-wrapper {
  position: relative;
}

input {
  display: none;
}

.menu-wrapper label {
  position: relative;
  width: 70px;
  height: 30px;
  top: 6px;
  cursor: pointer;
  background: transparent;
}

.menu-wrapper label:after,
.menu-wrapper input:checked + label:after {
  content: "";
  position: absolute;
  top: 50%;
  margin-top: -2px;
  width: 30px;
  height: 2px;
  border-radius: 2px;
  background: #42454a;
}

.menu-wrapper label .burger:before {
  content: "";
  position: absolute;
  top: 6px;
  width: 10px;
  left: 20px;
  height: 2px;
  border-radius: 2px;
  background: #42454a;
}

.menu-wrapper label .burger:after {
  content: "";
  position: absolute;
  bottom: 8px;
  width: 30px;
  height: 2px;
  border-radius: 2px;
  background: #42454a;
}

/* Menu wrapper for mobile and desktop */
.menu-list-wrapper {
  display: none; /* Hidden by default */
}

/* Fullscreen menu for mobile */
.fullscreen-menu {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.9);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 999;
}

.menu-list {
  list-style: none;
  padding: 0;
  margin: 0;
  text-align: center;
}

.menu-list li {
  margin: 20px 0;
}

.menu-list li a {
  text-decoration: none;
  font-size: 16px;
  color: #ffffff;
  transition: color 0.3s ease;
}

.menu-list li a:hover {
  color: #1e90ff; /* Example hover color */
  font-weight: bold;
}

/* Inline menu for desktop */
.menu-inline {
  display: flex;
  gap: 20px;
  background: none; /* Remove fullscreen background */
}

.menu-inline li {
  margin: 0;
}

.menu-inline li a {
  color: #000; /* Desktop inline menu text color */
}

/* Transition effects */
.menu-slide-enter-active,
.menu-slide-leave-active {
  transition: transform 0.5s ease, opacity 0.5s ease;
}

.menu-slide-enter-from {
  transform: translateY(-100%);
  opacity: 0;
}

.menu-slide-enter-to {
  transform: translateY(0);
  opacity: 1;
}

.menu-slide-leave-from {
  transform: translateY(0);
  opacity: 1;
}

.menu-slide-leave-to {
  transform: translateY(-100%);
  opacity: 0;
}

/* Desktop styles */
@media (min-width: 992px) {
  .menu-list-wrapper {
    display: block !important; /* Always show inline menu on desktop */
    position: static;
    background: none;
  }

  label {
    display: none; /* Hide burger menu on desktop */
  }

  .menu-list {
    display: flex;
    gap: 20px;
  }

  .menu-list li {
    margin: 0;
  }
}

/* Mobile styles */
@media (max-width: 991px) {
  .menu-wrapper label {
    display: block;
  }
}
</style>
