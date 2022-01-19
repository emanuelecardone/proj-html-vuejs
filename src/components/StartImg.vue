<template>
    <!-- StartImg è un "bricolage" di immagini messe una sopra l'altra a partire da un'immagine base (per riprodurre la stessa immagine dello screenshot)
    Ogni parte mancante dell'immagine viene posizionata con position absolute, anche StartImg stessa ha position absolute essendo posizionata nel banner con l'effetto di sbordare
    Vengono stampate con v-for tutte le immagini le cui sources vengono prese come props -->
    <div class="start_img position-absolute">
        <img v-for="image,index in sources" :key="index" :src="require('../assets/img/' + image + '.png')" :alt="'Immagine di ' + image" :class="image">
    </div>
</template>

<script>
export default {
    name: 'StartImg',
    props: {
        sources: Array
    }    
}
</script>

<style lang="scss" scoped>

    .start_img{
        width: 100%;
        right: 0;

        > img{
            position: absolute;

            /* Modifica size e position delle immagini (base + secondarie) */
            &.base{
                width: 700px;
                left: 0;
                top: 50%;
                transform: translateY(-50%);
            }
            &.moon{
                top: 22%;
                left: 25%;
                filter: grayscale(100%) brightness(1.1);
            }
            &.book1{
                width: 220px;
                top: 18%;
                left: 82%;
            }
            &.book2{
                width: 260px;
                top: 60%;
                left: 48%;
            }
            &.bubblespeech{
                top: 8%;
                left: 108%;
            }
            &.magnifier{
                width: 80px;
                top: 71%;
                left: 102%;
            }
        }
    }
</style>