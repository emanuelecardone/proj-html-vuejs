<template>
    <header>
        <NavbarUp :thisData="upData" />
        <NavbarDown />
    </header>
</template>

<script>
import NavbarUp from './NavbarUp.vue';
import NavbarDown from './NavbarDown.vue';

export default {
    name: 'Header',
    components: {
        NavbarUp,
        NavbarDown
    },
    props: {
        upData: Object
    }
}
</script>

<style lang="scss" scoped>

    header{
        height: 160px;
        background-color: white;
    }
</style>