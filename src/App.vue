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
    handleSearchEvent() {
      console.log("Sono in search event", this.store.searchText);
    },

    getFilm() {

      let url = 'https://api.themoviedb.org/3/search/movie?';

      axios
        .get(url, {
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

          this.store.movies = response.data.results;
        });
    }

  },//methods


}//export

</script>

<template>

  <AppSearch @performSearch="getFilm" />

  <AppMain />


</template>

<style lang="scss">



</style>
