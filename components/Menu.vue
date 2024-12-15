<template>
  <div class="container">
    <input id="click" name="exit" type="checkbox" @click="menuToggle" />
    <label for="click"><span class="burger"></span></label>
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

.container label:before,
.container input:checked + label:before {
  content: "";
  position: absolute;
  top: 50%;
  margin-top: -2px;
  width: 30px;
  height: 2px;
  border-radius: 2px;
  background: #42454a;
}

.container label:before {
  -webkit-animation: animationOneReverse 1s ease forwards;
  animation: animationOneReverse 1s ease forwards;
}

@-webkit-keyframes animationOneReverse {
  0% {
    -webkit-transform: rotate(315deg);
  }
  25% {
    -webkit-transform: rotate(360deg);
  }
  50%,
  100% {
    -webkit-transform: rotate(0deg);
  }
}
@keyframes animationOneReverse {
  0% {
    transform: rotate(315deg);
  }
  25% {
    transform: rotate(360deg);
  }
  50%,
  100% {
    transform: rotate(0deg);
  }
}

.container input:checked + label:before {
  -webkit-animation: animationOne 1s ease forwards;
  animation: animationOne 1s ease forwards;
}

@-webkit-keyframes animationOne {
  0%,
  50% {
    -webkit-transform: rotate(0deg);
  }
  75% {
    -webkit-transform: rotate(360deg);
  }
  100% {
    -webkit-transform: rotate(315deg);
  }
}
@keyframes animationOne {
  0%,
  50% {
    transform: rotate(0deg);
  }
  75% {
    transform: rotate(360deg);
  }
  100% {
    transform: rotate(315deg);
  }
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

.container label:after {
  -webkit-animation: animationTwoReverse 1s ease forwards;
  animation: animationTwoReverse 1s ease forwards;
}

@-webkit-keyframes animationTwoReverse {
  0% {
    -webkit-transform: rotate(405deg);
  }
  25% {
    -webkit-transform: rotate(450deg);
  }
  50%,
  100% {
    -webkit-transform: rotate(0deg);
  }
}
@keyframes animationTwoReverse {
  0% {
    transform: rotate(405deg);
  }
  25% {
    transform: rotate(450deg);
  }
  50%,
  100% {
    transform: rotate(0deg);
  }
}

.container input:checked + label:after {
  -webkit-animation: animationTwo 1s ease forwards;
  animation: animationTwo 1s ease forwards;
}

@-webkit-keyframes animationTwo {
  0%,
  50% {
    -webkit-transform: rotate(0deg);
  }
  75% {
    -webkit-transform: rotate(450deg);
  }
  100% {
    -webkit-transform: rotate(405deg);
  }
}
@keyframes animationTwo {
  0%,
  50% {
    transform: rotate(0deg);
  }
  75% {
    transform: rotate(450deg);
  }
  100% {
    transform: rotate(405deg);
  }
}

/* Burger Icon */

.container label .burger:before {
  content: "";
  position: absolute;
  top: 6px;
  width: 10px;
  left: 20px;
  height: 2px;
  border-radius: 2px;
  background: #42454a;
  -webkit-animation: animationBurgerTopReverse 1s ease forwards;
  animation: animationBurgerTopReverse 1s ease forwards;
}

@-webkit-keyframes animationBurgerTopReverse {
  0%,
  50% {
    -webkit-transform: translateY(12px);
    opacity: 0;
  }
  51% {
    -webkit-transform: translateY(12px);
    opacity: 1;
  }
  100% {
    -webkit-transform: translateY(0px);
    opacity: 1;
  }
}
@keyframes animationBurgerTopReverse {
  0%,
  50% {
    transform: translateY(12px);
    opacity: 0;
  }
  51% {
    transform: translateY(12px);
    opacity: 1;
  }
  100% {
    transform: translateY(0px);
    opacity: 1;
  }
}

.container input:checked + label .burger:before {
  -webkit-animation: animationBurgerTop 1s ease forwards;
  animation: animationBurgerTop 1s ease forwards;
}

@-webkit-keyframes animationBurgerTop {
  0% {
    -webkit-transform: translateY(0px);
    opacity: 1;
  }
  50% {
    -webkit-transform: translateY(12px);
    opacity: 1;
  }
  51%,
  100% {
    -webkit-transform: translateY(12px);
    opacity: 0;
  }
}
@keyframes animationBurgerTop {
  0% {
    transform: translateY(0px);
    opacity: 1;
  }
  50% {
    transform: translateY(12px);
    opacity: 1;
  }
  51%,
  100% {
    transform: translateY(12px);
    opacity: 0;
  }
}

.container label .burger:after {
  content: "";
  position: absolute;
  bottom: 8px;
  width: 30px;
  height: 2px;
  border-radius: 2px;
  background: #42454a;
  -webkit-animation: animationBurgerBottomReverse 1s ease forwards;
  animation: animationBurgerBottomReverse 1s ease forwards;
}

@-webkit-keyframes animationBurgerBottomReverse {
  0%,
  50% {
    -webkit-transform: translateY(-12px);
    opacity: 0;
  }
  51% {
    -webkit-transform: translateY(-12px);
    opacity: 1;
  }
  100% {
    -webkit-transform: translateY(0px);
    opacity: 1;
  }
}
@keyframes animationBurgerBottomReverse {
  0%,
  50% {
    transform: translateY(-12px);
    opacity: 0;
  }
  51% {
    transform: translateY(-12px);
    opacity: 1;
  }
  100% {
    transform: translateY(0px);
    opacity: 1;
  }
}

.container input:checked + label .burger:after {
  -webkit-animation: animationBurgerBottom 1s ease forwards;
  animation: animationBurgerBottom 1s ease forwards;
}

@-webkit-keyframes animationBurgerBottom {
  0% {
    -webkit-transform: translateY(0px);
    opacity: 1;
  }
  50% {
    -webkit-transform: translateY(-12px);
    opacity: 1;
  }
  51%,
  100% {
    -webkit-transform: translateY(-12px);
    opacity: 0;
  }
}
@keyframes animationBurgerBottom {
  0% {
    transform: translateY(0px);
    opacity: 1;
  }
  50% {
    transform: translateY(-12px);
    opacity: 1;
  }
  51%,
  100% {
    transform: translateY(-12px);
    opacity: 0;
  }
}

@media (max-width: 992px) {
  span.menu {
    font-size: 14px;
  }

  .container label {
    height: 26px;
  }
}
</style>
