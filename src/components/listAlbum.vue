<template>
  <li class="characters">
    <figure class="img-container">
      <img :src="characters.poster" alt="" />
    </figure>
    <h5 class="titolo">{{ characters.title }}</h5>
    <p class="autore">{{ characters.author }}</p>
    <span class="anno">{{ characters.year }}</span>
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
$grey: #2e3a46;
$textColorWhite: white;

.characters {
  width: calc((100% / 5) - 20px);
  flex-grow: 1;
  padding: 12px;
  background: $grey;
  text-align: center;
  color: $textColorWhite;
  box-shadow: 5px 5px 5px #131314;
  transition: 0.5s;
  cursor: pointer;

  &:hover {
    transition: all 0.5s;
    transform: scale(1.1);
    border-radius: 10px;
    background: #47596c;
  }

  figure {
    aspect-ratio: 1 / 1;
    overflow: hidden;

    img {
      max-width: 100%;
    }
  }
  .titolo {
    margin: 10px 0;
    text-transform: uppercase;
  }

  .autore,
  .anno {
    color: #80807f;
    font-size: 12px;
  }
}
</style>
