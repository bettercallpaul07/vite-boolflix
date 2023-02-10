<script>

import {store} from "../store.js";


  export default {
    name: "AppMain",
    data() {
        return {
                store
        };
             },

             computed: {
                cover() {
                    const initialUrl = "https://image.tmdb.org/t/p/";
                    const coverSize = "w342";
                    const posterPath = this.movie.poster_path

                    return initialUrl + coverSize + posterPath;
                }, 

                vote() {
                    let newVote = this.movie.vote_average
                    newVote = Math.ceil(newVote/2)

                    console.log(newVote);

                    return newVote
                }


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

            <div>
                <img :src=cover alt="">
            </div>

            <h4>
                <p> {{ vote }}</p>
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

            <div>
                <img src="" alt="">
            </div>

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

    width: 30px;
    height: 30px;

    img {
        width: 100%;
        height: 100%;
        border-radius: 50%;
        border: 1px solid black;
    }

}



</style>