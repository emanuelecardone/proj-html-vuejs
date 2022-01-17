<template>
    <div class="banner w-100 h_500p d-flex justify-content-center align-items-center">
        <div class="text_section d-flex flex-column align-items-start" :class="{'w_60': type === 'start', 'w-50': type === 'learning'}">
            <h1 v-if="type === 'start'">{{content.title}}</h1>
            <h2 v-else class="fs_40">{{content.title}}</h2>
            <p class="my-5 fs_30">
                {{content.text}}
            </p>
            <Button :type="'text'" :text="content.btnText" />
        </div>
        <div class="img_section position-relative h-100" :class="{'w_40': type === 'start', 'w-50': type === 'learning'}">
            <StartImg v-if="type === 'start'" :sources="content.imgSrc" />
            <img v-else :src="require('../assets/img' + content.imgSrc + '.png')" alt="Immagine banner" class="position-absolute">
        </div>
    </div>
</template>

<script>
import StartImg from './StartImg.vue';
import Button from './Button.vue';

export default {
    name: 'Banner',
    components: {
        StartImg,
        Button
    },
    props: {
        type: String,
        content: Object
    }    
}
</script>

<style lang="scss" scoped>

    .banner{
        padding: 0 400px;

        .text_section{
            padding: 100px 0;

            h1{
                font-size: 70px;
            }
        }
        .img_section{

            img{
                top: 50%;
                left: 0;
                transform: translateY(-50%);
            }
        }
    }
</style>