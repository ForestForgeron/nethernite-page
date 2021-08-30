<template>
  <div class="shop-page">
    <Header />
    <Shop />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Shop from "./components/Shop.vue";
export default {
  name: "App",
  components: {
    Header,
    Shop,
  },
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Roboto:wght@400;500;700&display=swap");

html,
body,
div,
p,
ul,
li,
button,
input,
textarea,
h1,
h2,
h3,
h4,
h5,
h6 {
  margin: 0;
  padding: 0;
  border-width: 0;
}

html {
  scroll-behavior: smooth;

  font-family: "Roboto", Arial, sans-serif;
  font-size: 16px;
}

button {
  cursor: pointer;
  transition: all 0.3s ease-in-out;
}

a {
  text-decoration: none;
}

li {
  list-style: none;
}

.shop-page {
  height: 100vh;

  overflow: hidden;

  background: no-repeat center url("assets/background-main.png");
  background-size: cover;
}
</style>
