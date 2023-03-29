<script>

import CardsElements from "./CardsElements.vue"

import CardSearch from "./CardSearch.vue"

import axios from "axios"

import {store} from "../store.js";



export default {
    data() {
        return {
            store,
        }

        
    },

    components:{
        CardsElements,
        CardSearch,
    },

    created() {
        axios.get(this.store.APIcall).then((res) => {
            console.log(res.data.data);

            this.store.cards = res.data.data;
        })
    },

    methods: {
        search() {
            let apiNewString = this.store.APIcall + this.store.APIquery + this.store.CardName;

            axios.get(apiNewString).then((res) => {
                console.log(res.data.data);

                this.store.cards =res.data.data;
            })
        }
    }
}
</script>

<template>
    <div>
        <div>
            <CardSearch @searchCardName="search()"></CardSearch>
        </div>

        <div id="cards">
            <CardsElements v-for="card in store.cards" :cards="card"></CardsElements>
        </div>
    </div>
</template> 

<style lang="scss" scoped>

#cards{
    display: flex;
    flex-flow: row wrap;
    gap: 20px;

    padding: 20px;
}
</style>