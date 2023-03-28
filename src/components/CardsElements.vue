<script>

export default {
    name: "CardsElements",

    data() {
        return{

        }
    },

     props: {
        cards: Object,
    }
 }
</script>

<template>
    <div class="card">
        <div class="container-img">
            <img :src="cards.card_images[0].image_url" alt="">
        </div>  

        <div>
           <b>Name: {{ cards.name }} </b>
        </div>   

        <div>
            <em>Race: {{ cards.race }}</em>
        </div>
        
        <div>
           <em>Type: {{ cards.type }} </em>
        </div>   
    </div>
</template>

<style lang="scss" scoped>
.card{
    padding: 20px;
    
    max-width: 200px;

    .container-img {
        width: 200px;

        img{
          width: 100%;
        }

    }
    
}
</style>