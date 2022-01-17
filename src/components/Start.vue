<template>
    <section class="start mb_120">
        <Banner :type="'start'" :content="bannerData" />
        <div class="infos_wrapper d-flex justify-content-between align-items-center mt_60 mb_120">
            <div v-for="info,index in infos" :key="index" class="single_info_wrapper p-4">
                <i :class="'info_icon fs_50 fas fa-' + info.icon"></i>
                <h6 class="info_title my-4">{{info.title}}</h6>
                <p class="info_text">{{info.text}}</p>
            </div>
        </div>
        <div class="images_wrapper d-flex justify-content-between text-capitalize">
            <div class="images_wrapper_left d-flex flex-wrap justify-content-between">
                <div v-for="image,index in images.left" :key="index" :class="{'align-self-end': index > 0, 'mt-4': index === 2}">
                    <img :src="require('../assets/img/' + image.src + '.jpg')" :alt="'Immagine di ' + image.title">
                    <div class="titles_img d-flex justify-content-between align-items-center">
                        <span class="image_title fs-5">{{image.title}}</span>
                        <span class="image_subtitle fs-6">{{image.subtitle}}</span>
                    </div>
                </div>
            </div>
            <div class="images_wrapper_right d-flex flex-column justify-content-between">
                <div v-for="image,index in images.right" :key="index">
                    <img :src="require('../assets/img/' + image.src + '.jpg')" :alt="'Immagine di ' + image.title">
                    <div class="titles_img d-flex justify-content-between align-items-center">
                        <span class="image_title fs-5">{{image.title}}</span>
                        <span class="image_subtitle fs-6">{{image.subtitle}}</span>
                    </div>
                </div>
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
            ],
            // Oggetto con src e test delle immagini
            images: {
                left: [
                    {
                        src: 'cat_1-770x375',
                        title: 'software development',
                        subtitle: '5 courses'
                    },
                    {
                        src: 'cat_4-370x155',
                        title: 'music',
                        subtitle: '5 courses'
                    },
                    {
                        src: 'cat_5-370x155',
                        title: 'exercise',
                        subtitle: '7 courses'
                    }
                ],
                right: [
                    {
                        src: 'cat_2-370x155',
                        title: 'art',
                        subtitle: '8 courses'
                    },
                    {
                        src: 'cat_3-370x155',
                        title: 'material design',
                        subtitle: '5 courses'
                    },
                    {
                        src: 'cat_6-370x155',
                        title: 'photography',
                        subtitle: '4 courses'
                    }
                ]
            }
        };
    }    
}
</script>

<style lang="scss" scoped>
@import '../style/variables.scss';

    .start{
        padding: 0 375px;

        .banner{
            height: 500px;
        }
    }
    .single_info_wrapper{
        background-color: #f2f6fb;
        width: 370px;
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
    .images_wrapper_left{
        max-width: 770px;
    }
    .image_title{
        color: $primary_color;
    }
    .image_subtitle{
        color: $tertiary_color;
    }
</style>