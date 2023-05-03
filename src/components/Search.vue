<template>
  <div class="search-container">
    <input
      type="text"
      v-model="searchText"
      @input="$emit('search-input', searchText)"
      placeholder="Cerca carta"
    />
    <select v-model="selectedType" @change="$emit('type-selected', selectedType)">
      <option value="">Seleziona tipo</option>
      <option v-for="type in cardTypes" :key="type" :value="type">{{ type }}</option>
    </select>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      searchText: "",
      selectedType: "",
      cardTypes: [],
    };
  },
  methods: {
    getCardTypes() {
      const apiUrl = "https://db.ygoprodeck.com/api/v7/cardinfo.php";
      axios.get(apiUrl).then((response) => {
        this.cardTypes = response.data.type;
      });
    },
  },
  mounted() {
    this.getCardTypes();
  },
};
</script>

<style scoped>
.search-container {
  display: flex;
  justify-content: center;
  gap: 20px;
  margin-bottom: 20px;
}
</style>
