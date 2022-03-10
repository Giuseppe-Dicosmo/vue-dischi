<template>
  <section class="container-Music">
    <ul class="container">
      characters: [],
      <li v-for="album in characters" :key="album.id" class="characters">
        {{album.name}}
      </li>
    </ul>
  </section>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      characters: [],
    };
  },
  methods: {
    personaggi: function () {
      axios
        .get("https://flynn.boolean.careers/exercises/api/array/music")
        .then((res) => {
          console.log("res.data", res.data);
          this.characters = res.data;
        });
    },
  },
  created() {
    this.personaggi()
  },
};
</script>

<style scoped lang="scss">
@import "../assets/scss/_style.scss";
$brand_white: white;

.container-Music {
  // border: 1px solid yellow;
  // display: flex;
  flex-grow: 1;
  height: 90%;

  .container {
    @include container;
    border: 1px solid yellow;
    color: $brand_white;
  }
}
</style>
