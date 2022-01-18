<template>
    <!-- Componente che contiene 5 stelle vuote o piene in base al numero di stelle piene definito da rate.amount nel data di Main
    Le stelle sono sempre 5, ma questo componente va bene per qualsiasi voto. fas è la classe "piene", far quella "vuote" -->
    <div class="rate_stars">
        <i class="fa-star" v-for="star,index in stars" :key="index" :class="{'fas': index < fullStars, 'far': index >= fullStars}"></i>
    </div>
</template>

<script>
export default {
    name: 'RateStars',
    props: {
        fullStars: Number
    },
    data: function(){
        return {
            // Numero di stelle
            stars: 5
        };
    }    
}
</script>

<style lang="scss" scoped>

    i.fas{
        color: #fecc4f;
    }
</style>