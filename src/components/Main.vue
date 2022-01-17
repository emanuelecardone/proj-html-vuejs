<template>
    <main>
        <Start />
        <Banner />
        <CoursesList />
        <Stats />
        <NewsLetter />
        <CoursesList />
        <JoinUs />
        <MasterStudy />
    </main>
</template>

<script>
import Start from './Start.vue';
import Banner from './Banner.vue';
import CoursesList from './CoursesList.vue';
import Stats from './Stats.vue';
import NewsLetter from './NewsLetter.vue';
import JoinUs from './JoinUs.vue';
import MasterStudy from './MasterStudy.vue';

export default {
    name: 'Main',
    components: {
        Start,
        Banner,
        CoursesList,
        Stats,
        NewsLetter,
        JoinUs,
        MasterStudy
    }
}
</script>

<style lang="scss" scoped>

</style>