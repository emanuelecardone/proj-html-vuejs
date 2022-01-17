<template>
    <main class="mt_80">
        <Start :bannerData="banners.start" />
        <Banner :type="'learning'" :content="banners.learning" />
        <CoursesList class="recent" />
        <Stats />
        <NewsLetter />
        <CoursesList class="popular" />
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
    },
    data: function(){
        return {
            // Oggetto con il contenuto per i banners
            banners: {
                start: {
                    title: 'Start Investing in You',
                    text: 'With over 1200 courses in 18 subjects, you\'re guaranteed to find something that\'s right for you.',
                    btnText: 'join for free',
                    imgSrc: [
                        'base',
                        'moon',
                        'book1',
                        'book2',
                        'bubblespeech',
                        'magnifier'
                    ] 
                },
                learning: {
                    title: 'Limitless learning, more possibilities',
                    text: 'Online courses open the opportunity for learning to almost anyone, regardless of their scheduling commitments.',
                    btnText: 'read more',
                    imgSrc: 'Untitled-1-1-1-1-1'
                }
            }
        };
    }
}
</script>

<style lang="scss" scoped>

    main{

        > .banner{
            background-color: #f0f4fa;
            padding: 375px;
        }
    }
</style>