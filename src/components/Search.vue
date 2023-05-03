<template>
  <div class="search-container">
    <input type="text" v-model="searchText" @input="emitSearch" placeholder="Cerca" />
    <select v-model="selectedType" @change="emitType">
      <option value="">Seleziona un tipo</option>
      <option value="Normal Monster">Monster</option>
      <option value="Spell Card">Spell Card</option>
      <option value="Trap Card">Trap Card</option>
    </select>
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
    },
    emitType() {
      this.$emit("type-selected", this.selectedType);
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
