<template>
  <li class="characters">
    <figure class="img-container">
      <img :src="characters.poster" alt="" />
    </figure>
  </li>
</template>

<script>
export default {
  props: {
    characters: {
      type: Object,
      require: true,
    },
  },
};
</script>

<style scoped lang="scss">
.characters {
  width: calc((100% / 6));
  cursor: pointer;

  figure {
    aspect-ratio: 1 / 1;
    overflow: hidden;

    img {
      max-width: 100%;
    }
  }
}
</style>
