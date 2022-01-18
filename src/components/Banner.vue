<template>
    <div class="row">
        <div :class="{'col-7': type === 'start', 'col-6': type === 'learning'}">
            <div class="text_section w-100 d-flex flex-column align-items-start">
                <h1 v-if="type === 'start'">{{content.title}}</h1>
                <h2 v-else class="fs_40">{{content.title}}</h2>
                <p class="my-4 fs_20">
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
    }
</style>