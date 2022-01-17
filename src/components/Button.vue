<template>
    <a href="#" class="btn page_btn"></a>
</template>

<script>
export default {
    name: 'Button',
    props: {
        text: String
    }    
}
</script>

<style lang="scss" scoped>
@import '../style/mixins.scss';

    .page_btn{
        @include page_btn;
    }
</style>