<template>
  <header class="nav">
    <figure>
      <img src="../assets/Spotify_icon-icons.com_66783.svg" alt="" />
    </figure>
  </header>
</template>

<script>
export default {
  name: "headerNav",
};
</script>

<style scoped lang="scss">
$grey: #2e3a46;
.nav {
  display: flex;
  align-items: center;
  height: 7%;
  padding: 0 10px;
  background: $grey;

  figure {
    height: 65%;
    aspect-ratio: 1 / 1;
  }
}
</style>
