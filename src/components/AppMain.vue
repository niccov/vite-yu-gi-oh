<script>

import axios from "axios"

import {store} from "../store.js";

import CardsElements from "./CardsElements.vue"

export default {
    data() {
        return {
            store,
            CardsElements,
        }
    },

    created() {
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=50&offset=0').then((res) => {
            console.log(res.data.data);

            this.store.cards = res.data.data;
        })
    }
}
</script>

<template>
    <div>
        <div id="Cards">
            <CardsElements></CardsElements>
        </div>
    </div>
</template> 

<style lang="scss" scoped></style>