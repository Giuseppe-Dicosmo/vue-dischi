<template>
  <header class="nav">
    <figure>
      <img src="../assets/Spotify_icon-icons.com_66783.svg" alt="" />
    </figure>
    <div class="container-select">
      <label for="cars">Che genere ascolti:</label>
      <select
        v-model="SelezioneGenere"
        @change="$emit('changeGenere', SelezioneGenere)"
        name="cars"
        id="cars"
      >
        <option value="all">All</option>
        <option value="metal">Metal</option>
        <option value="jazz">Jazz</option>
        <option value="pop">Pop</option>
        <option value="rock">Rock</option>
      </select>
    </div>
  </header>
</template>

<script>
export default {
  name: "headerNav",
  data() {
    return {
      SelezioneGenere: "",
    };
  },
};
</script>

<style scoped lang="scss">
$grey: #2e3a46;
$textColorWhite: white;

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

  .container-select {
    display: flex;
    align-items: center;
    width: 90%;
    margin: 0 auto;
    // border: 1px solid red;
    color: $textColorWhite;
    height: 100%;

    label {
      margin-right: 5px;
    }

    select,
    option {
      flex-grow: 1;
      background: #47596c;
      color: $textColorWhite;
    }

    select {
      height: 70%;
      border-radius: 3px;
      text-align: center;
      border: none;
    }
  }
}
</style>
