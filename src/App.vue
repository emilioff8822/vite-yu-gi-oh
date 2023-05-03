<template>
  <div id="app" class="page-wrapper">
    <div class="container">
      <Header />
      <Search @search-input="updateSearch" @type-selected="updateType" @reset-search="resetSearch" />
      <CardsContainer />
      <Footer />
    </div>
  </div>
</template>

<script>
import axios from "axios";
import { store } from "./data/store";
import Header from "./components/Header.vue";
import Search from "./components/Search.vue";
import CardsContainer from "./components/CardsContainer.vue";
import Footer from "./components/Footer.vue";
export default {
  name: "App",
  components: {
    Header,
    Search,
    CardsContainer,
    Footer,
  },
  methods: {
    getApi(searchText = "", type = "") {
      let url = `${store.apiUrl}?num=100&offset=0&type=${type}`;
      if (searchText !== "") {
        url += `&fname=${searchText}`;
      }
      axios.get(url).then((result) => {
        store.resultArray = result.data.data;
      });
    },
    updateSearch(searchText) {
      this.currentSearch = searchText;
      this.getApi(searchText, this.currentType);
    },
    updateType(type) {
      this.currentType = type;
      this.getApi(this.currentSearch, type);
    },
    resetSearch() {
      this.currentSearch = "";
      this.currentType = "";
      this.getApi(this.currentSearch, this.currentType);
    },
  },
  data() {
    return {
      currentSearch: "",
      currentType: "",
    };
  },
  mounted() {
    this.getApi();
  },
};
</script>


<style lang="scss">
@import "bootstrap/scss/bootstrap.scss";

.page-wrapper {
  background-color: orange;
  padding: 90px 90px;
  box-sizing: border-box;
  min-height: 100vh;
  position: relative;
}

.container {
  background-color: white;
  padding: 0;
  box-sizing: border-box;
  min-height: 100%;
  position: relative;
  top: -90px;
}

body {
  margin: 0;
}
</style>
