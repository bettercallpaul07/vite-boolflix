<script>
import axios from "axios";

import AppSearch from "./components/AppSearch.vue";
import AppMain from "./components/AppMain.vue";
import { store } from "./store.js";

export default {
  name: "App",
  data() {
    return {
      store
    };
  },

  components: {
    AppSearch,
    AppMain
  },//components

  methods: {

    searchEvent(){
      this.makeSearch("movie")
      this.makeSearch("tv") 
    },

    makeSearch(endpoint) {

      let url = 'https://api.themoviedb.org/3/search/';

      axios
        .get(url + endpoint, {
          params: {
            api_key: '02368db92224d475e889240283233038',
            query: this.store.searchText,
            language: 'it-IT'
          }
        })

        
        .then((response) => {
          console.log('------------------------------------');
          console.log(response);
          console.log('------------------------------------');

          if (endpoint == "movie") {
            this.store.movies = response.data.results;
          }

          else {
            // this.store.tv = response.data.results;
          }
    })

    },
  },//methods


}//export

</script>

<template>

  <AppSearch @performSearch="searchEvent()" />

  <AppMain />


</template>

<style lang="scss">

</style>
