<template>
  <section id="home" class="home-section">
    <div class="container">
      <img class="bg-shape" src="@/assets/images/ellipse.png" alt="bg-shape" />
      <img
        class="bg-ellipse-1"
        src="@/assets/images/ellipse-1.png"
        alt="bg-ellipse-1"
      />
      <img
        class="bg-ellipse-2"
        src="@/assets/images/ellipse-2.png"
        alt="bg-ellipse-2"
      />
      <div class="model-name"><p>EV-B</p></div>
      <div class="home-content">
        <div class="home-content__text">
          <p class="sub-banner">LET'S RIDE THE</p>
          <p class="banner">FUTURE</p>
          <p class="banner-paragraph">
            Simple and sleek design with users in mind. <br />
            Unbeatable prices, <strong>state-of-the-art</strong> features and
            <span class="emphasis">eco-friendly</span>!
          </p>
          <div class="home-content__text-btns">
            <a class="home-content__text__btns__preorder"> Preorder </a>
          </div>
        </div>
        <div class="home-content__product">
          <img
            src="@/assets/images/e_bike.png"
            alt="bike-img"
            class="home-content__bike-img"
          />
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "Banner",
};
</script>

<style lang="scss" scoped>
@use "@/assets/sass/colours.scss" as *;

.home-section {
  background-color: $blue-colour;
  height: 100vh;
  position: relative;
  width: 100vw;
}

.container {
  margin: 0 auto !important;
  max-width: 133rem !important;
  padding: 0 2.5rem !important;
  display: flex;
}

.bg-shape {
  position: absolute;
  right: 0;
  top: 0;
  z-index: 1;
  width: 50vw;
  height: 90vh;
}

.bg-ellipse-1 {
  position: absolute;
  right: 30%;
  top: -11%;
  z-index: 2;
  width: 15rem;
}

.bg-ellipse-2 {
  position: absolute;
  left: 10%;
  bottom: -1%;
  z-index: 2;
  width: 20rem;
}

.model-name {
  position: absolute;
  right: 15%;
  top: 25%;
  font-family: "neumaticlight";
  font-size: 120pt;
  font-weight: 100 !important;
  color: white;
  z-index: 2;
}

.model-name > p {
  animation: glow 5s ease-in-out infinite alternate;
}

@keyframes glow {
  from {
    text-shadow: 0 0 10px #d8e6ef, 0 0 20px #d8e6ef, 0 0 30px #d8e6ef,
      0 0 40px #d8e6ef, 0 0 50px #d8e6ef, 0 0 60px #d8e6ef, 0 0 70px #d8e6ef;
  }

  to {
    text-shadow: 0 0 20px #fff, 0 0 30px #bad3e3, 0 0 40px #bad3e3,
      0 0 50px #bad3e3, 0 0 60px #bad3e3, 0 0 70px #bad3e3, 0 0 80px #bad3e3;
  }
}

.home-content {
  align-items: center;
  display: flex;
  height: 100vh;
  position: relative;
  width: 100%;
  flex: 0 0 100%;
  /* flex-flow: row wrap; */
  justify-content: space-between;
}

.home-content__text {
  display: flex;
  flex-direction: column;
  margin-top: 5rem;
  max-width: 50rem;
  z-index: 3;
}

.home-content__bike-img {
  margin-top: 5rem;
  position: relative;
  right: 0;
  width: 80%;
  z-index: 3;
}

.sub-banner {
  font-size: 22pt;
  letter-spacing: 0.5cap;
}

.banner {
  font-size: 60pt;
  margin-top: -10px;
}

.banner-paragraph {
  font-size: 12pt;
  margin-top: -4px;
}

.emphasis {
  font-weight: bolder;
  color: #043f55;
}

.home-content__text-btns {
  display: flex;
  font-size: 1.4rem;
  gap: 1.5rem;
  align-items: center;
}
.home-content__text__btns__preorder {
  margin-top: 1rem;
  font-size: 14pt;
  align-items: center;
  color: #043f55;
  display: flex;
  text-decoration: none;
  border: 2px solid #043f55;
  border-radius: 2rem;
  padding: 1rem 1.5rem;
}

.home-content__text__btns__learn-more {
  background-color: #42454a;
  border: 2px solid #42454a;
  border-radius: 0.3rem;
  box-shadow: 0 10px 15px 0 rgba(34, 34, 34, 0.2);
  padding: 1rem 1.5rem;
  transition: all 0.3s;
}

@media (max-width: 992px) {
  .sub-banner {
    font-size: 18pt;
  }

  .banner {
    font-size: 56pt;
  }

  .banner-paragraph {
    font-size: 11pt;
  }

  .home-content__text-btns {
    font-size: 1rem;
    gap: 1rem;
  }

  .model-name {
    font-size: 110pt;
  }
}
</style>
