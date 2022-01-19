<template>
    <!-- La sezione banner parte sempre con una row dato il duplice utilizzo che lo rendeva necessario (lo richiamo dentro una col), quindi va sempre messo dentro un container come figlio diretto
    Prende come props il tipo di banner (per inquadrare in quale sezione lo sto utilizzando) e il contenuto da stampare in pagina -->
    <div class="row">
        <div :class="{'col-7': type === 'start', 'col-6': type === 'learning'}">
            <div class="text_section w-100 d-flex flex-column align-items-start">
                <h1 v-if="type === 'start'">{{content.title}}</h1>
                <h2 v-else class="fs_40">{{content.title}}</h2>
                <p class="mt-4 mb-5 fs_20">
                    {{content.text}}
                </p>
                <Button :type="'text'" :text="content.btnText" />
            </div>
        </div>
        <div :class="{'col-5': type === 'start', 'col-6': type === 'learning'}">
            <div v-if="type === 'start'" class="img_section w-100 h-100 position-relative">
                <StartImg :sources="content.imgSrc" class="h-100" />
            </div>
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
    .text_section{
        padding-top: 80px;
        padding-bottom: 80px;

        h1{
            font-size: 65px;
        }
        h2{
            font-size: 50px;
        }
        p{
            font-size: 30px;
        }
    }
</style>