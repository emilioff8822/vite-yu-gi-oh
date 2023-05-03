<template>
  <div class="search-container">
    <input type="text" v-model="searchText" placeholder="Cerca" />
    <select v-model="selectedType">
      <option value="">Seleziona un tipo</option>
      <option value="Normal Monster">Monster</option>
      <option value="Spell Card">Spell Card</option>
      <option value="Trap Card">Trap Card</option>
    </select>
    <button @click="emitSearch">Search</button>
    <button @click="reset">Reset</button>
  </div>
</template>

<script>
export default {
  name: "Search",
  data() {
    return {
      searchText: "",
      selectedType: "",
    };
  },
  methods: {
    emitSearch() {
      this.$emit("search-input", this.searchText);
      this.$emit("type-selected", this.selectedType);
    },
    reset() {
      this.searchText = "";
      this.selectedType = "";
      this.emitSearch();
      this.$emit("reset-search");
    },
  },
};
</script>
<style scoped>
.search-container {
  display: flex;
  justify-content: center;
  gap: 10px;
  margin-bottom: 20px;
}
</style>
