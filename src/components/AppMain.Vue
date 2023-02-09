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
            
            <div class="img-container">
                <img :src="`src/assets/flags/${movie.original_language}.svg`" :alt="`${movie.original_language}`">
            </div>


            <h6>
                {{ movie.release_date }}
            </h6>
            <p>
                {{ movie.overview }}
            </p>
        </div>

        <div v-for="series in store.tv">
            <h3>
                {{ series.name }}
            </h3>

            <h4>
                {{ series.vote_average }}
            </h4>
            
            <div class="img-container">
                <img :src="`src/assets/flags/${series.original_language}.svg`" :alt="`${series.original_language}`">
            </div>


            <h6>
                {{ series.release_date }}
            </h6>

        </div>
    </main> 




</template>

<style lang="scss">

.img-container {

    width: 20px;
    height: 20px;

    img {
        width: 100%;
        height: 100%;
        border-radius: 50%;
        border: 1px solid black;
    }

}



</style>