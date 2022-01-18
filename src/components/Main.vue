<template>
    <main>
        <Start :bannerData="banners.start" />
        <div class="second_banner w-100">
            <div class="container">
                <Banner :type="'learning'" :content="banners.learning" class="learning px_100 banner" />
            </div>
        </div>
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
                    btnText: 'read more'
                }
            }
        };
    }
}
</script>

<style lang="scss" scoped>

    main{

        .second_banner{
            background-image: url("../assets/img/Untitled-1-1-1-1-1.png");
            background-size: 103% 100%;
        }
    }
</style>