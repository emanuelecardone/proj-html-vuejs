<template>
    <!-- Il Button è un tag <a> e prende come props il tipo di button (data la presenza di pulsanti con un'icona invece che un testo) e l'eventuale testo interno -->
    <a href="#" class="btn page_btn d-flex justify-content-center align-items-center">
        <span v-if="type === 'text'">{{text}}</span>
        <i v-else class="fas fa-search"></i>
    </a>
</template>

<script>
export default {
    name: 'Button',
    props: {
        type: String,
        text: String
    }    
}
</script>

<style lang="scss" scoped>
@import '../style/mixins.scss';

    .page_btn{
        @include page_btn;

        &:hover{
            background-color: #4dd3ac;
            color: white;
        }
    }
</style>