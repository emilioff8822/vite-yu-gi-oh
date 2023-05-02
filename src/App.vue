

<script>
import axios from "axios";
import {store} from "./data/store";
import CardsContainer from "./components/CardsContainer.vue";
import Footer from "./components/Footer.vue";
import Header from "./components/Header.vue";
export default{
  name: "App",
  components:{
    CardsContainer,
    Footer,
    Header
  },
  methods:{
    getApi(){
      axios.get(store.apiUrl)
      .then(result => {
        store.resultArray = result.data.data;
      })
    }
  },
  mounted(){
    this.getApi();
  }
}
</script>

<template>
  <div class="page-wrapper">
    <div class="container">
      <Header/>
      <CardsContainer/>
      <Footer/>
    </div>
  </div>
</template>


<style lang="scss">
@import "bootstrap/scss/bootstrap.scss";

.page-wrapper {
  background-color: orange;
  padding: 90px  90px;
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
