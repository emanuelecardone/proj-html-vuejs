<template>
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
        width: 230px;
        right: 70px;

        > img{
            position: absolute;

            &.base{
                width: 160%;
                left: 0;
                top: 50%;
                transform: translateY(-50%);
            }
            &.moon{
                width: 42px;
                top: 30%;
                left: 28%;
                filter: grayscale(100%) brightness(1.1);
            }
            &.book1{
                width: 130px;
                top: 26%;
                left: 100%;
            }
            &.book2{
                width: 130px;
                top: 58%;
                left: 60%;
            }
            &.bubblespeech{
                width: 40px;
                top: 18%;
                left: 135%;
            }
            &.magnifier{
                width: 45px;
                top: 63%;
                left: 123%;
            }
        }
    }
</style>