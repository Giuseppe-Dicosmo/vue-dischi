<template>
  <div class="container-select">
    <label for="cars">Che genere ascolti:</label>
    <select v-model="selectedGenre" @change="$emit('changeGenre', selectedGenre)" name="cars" id="cars">
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
      selectedGenre: "",
    };
  },
  props: {
    characters: {
      type: String,
      require: true,
    },
  },
};
</script>

<style scoped lang="scss">
.container-select {
  display: flex;
  justify-content: start;
  flex-direction: column;
  border: 1px solid red;
  height: 100%;
}
</style>
