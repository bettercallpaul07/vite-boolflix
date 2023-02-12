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

        <AppCard
        v-for="movie in store.movies"
        :element="movie"
        />

        <h2>SerieTV</h2>

        <AppCard
        v-for="singleSeries in store.tv"
        :element="singleSeries"
        />

    </main>

</template>

<style lang="scss">

</style>