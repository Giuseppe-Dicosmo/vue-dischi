<template>
  <main class="container-Music">
    <ul class="container">
      <listAlbum
        v-for="(album, index) in characters"
        :key="index"
        :characters="album"
      />
    </ul>
  </main>
</template>

<script>
import axios from "axios";
import listAlbum from "./listAlbum.vue";

export default {
  components: {
    listAlbum,
  },
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
          this.characters = res.data.response;
        });
    },
  },
  created() {
    this.personaggi();
  },
};
</script>

<style scoped lang="scss">
@import "../assets/scss/_style.scss";

.container-Music {
  // border: 1px solid yellow;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-grow: 1;

  .container {
    @include container;
    width: 60vw;
    // border: 1px solid yellow;
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
    list-style-type: none;
  }
}
</style>
