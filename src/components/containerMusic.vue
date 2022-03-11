<template>
  <main class="container-Music">
    <selectAlbum @changeGenre="getSelectedGenre" />
    <ul class="container">
      <listAlbum
        v-for="(album, index) in filteredAlbum"
        :key="index"
        :characters="album"
      />
    </ul>
  </main>
</template>

<script>
import axios from "axios";
import selectAlbum from "./selectAlbum.vue";
import listAlbum from "./listAlbum.vue";

export default {
  components: {
    selectAlbum,
    listAlbum,
  },
  data() {
    return {
      characters: [],
      genreToFilter: "",
    };
  },
  computed: {
    filteredAlbum() {
      if (this.genreToFilter === "") {
        return this.characters;
      }
      return this.characters.filter((item) => {
        const { genre } = item;
        return genre.toLowerCase().includes();
        // item.genre === this.genreToFilter
      });
    },
  },
  methods: {
    getSelectedGenre: function (selectedGenre) {
      this.genreToFilter = selectedGenre;
    },
    personaggi: function () {
      axios
        .get("https://flynn.boolean.careers/exercises/api/array/music")
        .then((res) => {
          // console.log("res.data", res.data);
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
  // flex-direction: column;
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
