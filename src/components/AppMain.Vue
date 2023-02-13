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

        <div class="container">

            <AppCard
            v-for="movie in store.movies"
            :element="movie"
            />

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
        padding: 10px;
        width: 20%;
    }

}


</style>