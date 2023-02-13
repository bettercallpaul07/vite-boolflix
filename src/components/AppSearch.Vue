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
        <div class="logo">
            <h1>Boolflix</h1> 
        </div>
        <div>
            <input type="text" v-model="store.searchText" placeholder="Inserisci il nome di un film">
            <button @click="$emit('performSearch')">
                Search
            </button>
        </div>
    </header>



  

</template>

<style lang="scss" scoped>
header  {
    padding: 15px;
    background-color: black;
    display: flex;
    align-items: center;
    justify-content: space-between;
    height: 70px;
    width: 100%;

    .logo {
        color: red;
        font-weight: bold;
        font-size: large;

        h1 {
            text-transform: uppercase;
        }
    }


}

</style>