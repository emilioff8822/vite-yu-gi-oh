<script>
import axios from "axios";
import {store} from "./data/store";
import CardsContainer from "./components/CardsContainer.vue";
import Footer from "./components/Footer.vue";
export default{
  name: "App",
  components:{
    CardsContainer,
    Footer
  },
  methods:{
    getApi(){
      axios.get(store.apiUrl)
      .then(result => {
        store.resultArray = result.data.data; // Accedo alla proprietà "data" dell'oggetto restituito
      })
    }
  },
  mounted(){
    this.getApi();
  }
}
</script>

<template>
  <div class="container">
    <CardsContainer/>
    <Footer/>
  </div>
</template>

<style lang="scss">
@import "bootstrap/scss/bootstrap.scss";
</style>
