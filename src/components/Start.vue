<template>
    <section class="start">
        <Banner :type="'start'" :content="bannerData" />
    </section>
</template>

<script>
import Banner from './Banner.vue';

export default {
    name: 'Start',
    components: {
        Banner
    },
    props: {
        bannerData: Object
    }    
}
</script>

<style lang="scss" scoped>

</style>