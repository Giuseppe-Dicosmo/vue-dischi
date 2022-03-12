<template>
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
</template>

<script>
export default {
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
</style>
