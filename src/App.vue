<template>
  <main id="app">
    <headerNav />
    <containerMusic />
  </main>
</template>

<script>
import headerNav from "./components/headerNav.vue";
import containerMusic from "./components/containerMusic.vue";

export default {
  name: "App",
  components: {
    headerNav,
    containerMusic,
  },
};
</script>

<style lang="scss">
@import "./assets/scss/_style.scss";
$brand_white: white;

* {
  @include reset;
}

#app {
  // border: 1px solid red;
  width: 100%;
  height: 100vh;
  background: #1e2d3b;
  color: white;
  font-family: "assistant", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  // text-align: center;
}
</style>
