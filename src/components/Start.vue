<template>
    <section class="start">
        <Banner :type="'start'" :content="bannerData" />
        <div class="infos_wrapper d-flex justify-content-between align-items-center mt_60">
            <div v-for="info,index in infos" :key="index" class="single_info_wrapper p-4" :class="{'mx_5_percent': index === 1}">
                <i :class="'info_icon fs_50 fas fa-' + info.icon"></i>
                <h6 class="info_title my-4">{{info.title}}</h6>
                <p class="info_text">{{info.text}}</p>
            </div>
        </div>
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
    },
    data: function(){
        return {
            // Array con i testi delle info box
            infos: [
                {   
                    icon: 'globe-americas',
                    title: 'Worldwide Recognize',
                    text: 'Our online course certificates can be used around the world and also in most popular universities and companies.'
                },
                {   
                    icon: 'desktop',
                    title: 'Mostly Online Learning (sd)',
                    text: 'Masterstudy online certificates can be obtained in a range of specialized areas and typically take about a year to complete.'
                },
                {   
                    icon: 'calendar-check',
                    title: 'Graduate in as little as 1 Year',
                    text: 'Online post-graduate certificates are a popular way to develop your professional qualifications of Masterstudy'
                }
            ]
        };
    }    
}
</script>

<style lang="scss" scoped>
@import '../style/variables.scss';

    .start{
        padding: 0 350px;
    }
    .single_info_wrapper{
        background-color: #f2f6fb;
        width: 30%;
        height: 250px;
        display: flex;
        flex-direction: column;

        .info_icon{
            color: $secondary_color;
        }
        .info_title{
            color: $primary_color;
        }
        .info_text{
            color: $tertiary_color;
        }
    }
</style>