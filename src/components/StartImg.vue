<template>
    <div class="start_img w-100 h-100 position-relative">
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

        > img{
            position: absolute;

            &.base{
                left: 0;
                top: 50%;
                transform: translateY(-50%);
            }
            &.moon{
                top: 27%;
                left: 23%;
                filter: grayscale(100%) brightness(1.1);
            }
            &.book1{
                top: 25%;
                left: 83%;
            }
            &.book2{
                top: 58%;
                left: 50%;
            }
            &.bubblespeech{
                top: 15%;
                left: 110%;
            }
            &.magnifier{
                top: 67%;
                left: 103%;
            }
        }
    }
</style>