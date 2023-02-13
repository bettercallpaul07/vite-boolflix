<script>

import {store} from "../store.js";
import AppCard from "./AppCard.vue";

  export default {
    name: "AppMain",
    data() {
        return {
                store
        };
            },
            components: {
                AppCard
             },

            }//export

</script>

<template>
    <main>
        <h2>Film</h2>

        <div class="container">
            <AppCard
            v-for="movie in store.movies"
            :element="movie"
            />

            <h2>SerieTV</h2>

            <AppCard
            v-for="singleSeries in store.tv"
            :element="singleSeries"
            />

        </div>


    </main>

</template>

<style lang="scss" scoped>

main {
    h2 {
        color: white;
    }
    
}


.container {
    display: flex;
    flex-wrap: wrap;

    * {
        width: 20%;
    }

}


</style>