<script>

import {store} from "../store.js";


  export default {
    name: "AppMain",
    data() {
        return {
                store
        };
             },

    components: {
    },//components

    methods: {

 

    }//methods,

    }//export

</script>

<template>
    <main>
        <div v-for="movie in store.movies">
            <h3>
                {{ movie.title }}
            </h3>

            <h4>
                {{ movie.vote_average }}
            </h4>

            <span>
                <img :src="`../assets/flags/${movie.original_language}.svg`" :alt="`${movie.original_language}`">
            </span> 


            <h6>
                {{ movie.release_date }}
            </h6>
            <p>
                {{ movie.overview }}
            </p>
        </div>
    </main> 




</template>

<style lang="scss">

</style>