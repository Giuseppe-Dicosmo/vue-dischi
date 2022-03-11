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
  }
};
</script>

<style lang="scss">
@import "./assets/scss/_style.scss";

* {
  @include reset;
}

#app {
  // border: 1px solid red;
  display: flex;
  flex-direction: column;
  height: 100vh;
  background: #1e2d3b;
  font-family: "assistant", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  // text-align: center;
}
</style>
