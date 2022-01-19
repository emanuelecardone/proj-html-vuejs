<template>
    <!-- Sezione start: richiama inizialmente il componente banner passandogli i dati da stampare (testo e immagine)
    Poi usa il sistema row e cols per stampare le info e le immagini -->
    <section class="start mt_120 mb_120">
        <div class="container">
            <div class="row row-cols-1">
                <!-- Importo il banner dentro la col (da ricordare che il banner è una row) -->
                <div class="col">
                    <Banner :type="'start'" :content="bannerData" class="mb_120" />
                </div>
            </div>
        </div>
        <!-- Cards con le info -->
        <div class="infos_wrapper mb_120">
            <div class="container">
                <div class="row row-cols-3">
                    <div class="col" v-for="info,index in infos" :key="index" >
                        <div  class="single_info_wrapper w-100 h-100 p-4">
                            <i :class="'info_icon fs_50 fas fa-' + info.icon"></i>
                            <h6 class="info_title my-4">{{info.title}}</h6>
                            <p class="info_text">{{info.text}}</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <!-- Sezione con immagini -->
        <div class="images_wrapper text-capitalize">
            <div class="container">
                <div class="row row-cols-1 gy-3">
                    <div class="col">
                        <div class="row">
                            <div class="col-8">
                                <div class="single_image">
                                    <img :src="images.up.development.src" alt="Immagine sviluppo software">
                                    <div class="single_image_description">
                                        <span class="image_title">{{images.up.development.title}}</span>
                                        <span class="image_subtitle">{{images.up.development.subtitle}}</span>
                                    </div>
                                </div>
                            </div>
                            <div class="col-4">
                                <div class="small_images_wrapper w-100 h-100 d-flex flex-column justify-content-between align-items-center">
                                    <div class="single_image">
                                        <img :src="images.up.art.src" alt="Immagine art">
                                        <div class="single_image_description">
                                            <span class="image_title">{{images.up.art.title}}</span>
                                            <span class="image_subtitle">{{images.up.art.subtitle}}</span>
                                        </div>
                                    </div>
                                    <div class="single_image">
                                        <img :src="images.up.design.src" alt="Immagine design">
                                        <div class="single_image_description">
                                            <span class="image_title">{{images.up.design.title}}</span>
                                            <span class="image_subtitle">{{images.up.design.subtitle}}</span>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                    <div class="col">
                        <div class="row row-cols-3">
                            <div class="col" v-for="image,index in images.down" :key="index">
                                <div class="single_image">
                                    <img :src="require('../assets/img/' + image.src + '.jpg')" alt="Immagine design">
                                    <div class="single_image_description">
                                        <span class="image_title">{{image.title}}</span>
                                        <span class="image_subtitle">{{image.subtitle}}</span>
                                    </div>
                                </div>
                            </div>
                        </div>
                        <div class="images_wrapper_down w-100 h-100 d-flex justify-content-between align-items-center">
                            
                        </div>
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
                // Up è un oggetto data la diversa dimensione delle immagini
                up: {
                    development: {
                        src: require('../assets/img/cat_1-770x375.jpg'),
                        title: 'software development',
                        subtitle: '5 courses'
                    },
                    art: {
                        src: require('../assets/img/cat_2-370x155.jpg'),
                        title: 'art',
                        subtitle: '8 courses'
                    },
                    design: {
                        src: require('../assets/img/cat_3-370x155.jpg'),
                        title: 'material design',
                        subtitle: '5 courses'
                    }
                },
                // Down va bene come array in quanto posso ciclarlo
                down: [
                    {
                        src: 'cat_4-370x155',
                        title: 'music',
                        subtitle: '5 courses'
                    },
                    {
                        src: 'cat_5-370x155',
                        title: 'exercise',
                        subtitle: '7 courses'
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

    .single_info_wrapper{
        background-color: #f2f6fb;
        width: 30%;
        display: flex;
        flex-direction: column;
        cursor: pointer;

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

    .images_wrapper{

        .single_image{
            width: 100%;

            &_description{
                display: flex;
                justify-content: space-between;
                align-items: center;
                padding: 10px 0;
            }
        }
        img{
            width: 100%;
        }
        .image_title{
            color: $primary_color;
        }
        .image_subtitle{
            color: $tertiary_color;
        }
    }
    
</style>