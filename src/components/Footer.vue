<script>
import {store} from "../data/store";
export default {
  name: "Footer",
  data(){
    return{
      store
    }
  }
}
</script>

<template>
  <p class="text-center my-5">Sono state caricate {{ store.resultArray.length }} carte</p>
</template>

<style>

</style>
