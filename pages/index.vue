<template>
  <div>
    <Header></Header>
    <Banner></Banner>
    
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Banner from "./components/Banner.vue";

export default {
  name: "Index",
  components: {
    Header,
    Banner,
  },
};
</script>

<style scoped></style>
