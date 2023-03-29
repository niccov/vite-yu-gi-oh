<script>

import {store} from "../store.js"

export default {

    name: "CardSearch",
    data() {
        return{

            searchString: '?name=nomeinserito',

            store,
        }
    },

    
}
</script>

<template>
    <div id="search">
       <input v-model="store.CardName" type="text" placeholder="Scrivi il nome di una carta...">
       <button @click="$emit('searchCardName')">Cerca</button>
    </div>   
</template>

<style lang="scss" scoped>

#search{

    margin-left: 100px;
    input{
        width: 280px;
        height: 25px;

    }

    button{
        margin-left: 10px;
        padding: 6px 10px;
    }
}

</style>