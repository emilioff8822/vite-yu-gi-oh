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
  <h2 class="text-center my-5">Sono state caricate {{ store.resultArray.length }} carte</h2>
</template>

<style>

</style>
