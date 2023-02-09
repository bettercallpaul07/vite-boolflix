<script>
import {store} from "../store";


  export default {
    name: "AppSearch",
    data() {
        return {
            store
        };
    },
    components: {
    },//components
    methods: {

    },//methods
 
}//export

</script>

<template>

    <header>
        <div>
            <input type="text" v-model="store.searchText" placeholder="Inserisci il nome di un film">
            <button @click="$emit('performSearch')">
                Search
            </button>
        </div>
    </header>


  

</template>

<style lang="scss">

</style>