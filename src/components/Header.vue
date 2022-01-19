<template>
    <!-- L'header importa 2 navbar e passa alla nav superiore il contenuto da stampare proveniente da App -->
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