<template>
    <div class="banner w-100">
        <div class="banner_subwrapper w-100 h-100 d-flex justify-content-center align-items-center position-relative">
            <div class="text_section d-flex flex-column align-items-start" :class="{'w_60': type === 'start', 'w-50 learning position-absolute': type === 'learning'}">
                <h1 v-if="type === 'start'">{{content.title}}</h1>
                <h2 v-else class="fs_40">{{content.title}}</h2>
                <p class="my-5 fs_30">
                    {{content.text}}
                </p>
                <Button :type="'text'" :text="content.btnText" />
            </div>
            <div v-if="type === 'start'" class="img_section w_40 h-100">
                <StartImg :sources="content.imgSrc" />
            </div>
            <img v-else :src="require('../assets/img/' + content.imgSrc + '.png')" alt="Immagine banner" class="learning_img position-absolute">
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

        .text_section{
            padding: 100px 0;
            z-index: 2000;

            h1{
                font-size: 70px;
            }

            &.learning{
                left: 0;
                top: 50%;
                transform: translateY(-50%);
            }
        }
        .img_section{

            img{
                top: 50%;
                left: 0;
                transform: translateY(-50%);
            }
            .learning_img{
                top: 0;
                left: 0;
                z-index: 1000;
            }
        }
    }
</style>