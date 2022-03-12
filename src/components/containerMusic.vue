<template>
  <main class="container-Music">
    <!-- <selectAlbum @changeGenere="FunzioneSelezioneGenere" /> -->
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
// import selectAlbum from "./selectAlbum.vue";
import listAlbum from "./listAlbum.vue";

export default {
  components: {
    // selectAlbum,
    listAlbum,
  },
  data() {
    return {
      characters: [],
    };
  },
  props: {
    genereMusic: {
      type: String,
      default: "",
    },
  },
  computed: {
    filteredAlbum() {
      if (this.genereMusic === "" || this.genereMusic === "all") {
        return this.characters;
      }

      return this.characters.filter((element) => {
        const { genre } = element;

        return genre.toLowerCase().includes(this.genereMusic.toLowerCase());
      });
    },
  },
  methods: {
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
