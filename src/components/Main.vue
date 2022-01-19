<template>
    <!-- Il Main ha vari sottocomponenti ed è il componente che gestisce tutti i sottocomponenti appunto del main, contiente quasi tutti i data delle sottosezioni e le passa come props -->
    <main>
        <Start :bannerData="banners.start" />
        <div class="second_banner w-100">
            <div class="container">
                <!-- Da ricordare che banner è una row quindi lo metto come direct child di container -->
                <Banner :type="'learning'" :content="banners.learning" class="learning banner" />
            </div>
        </div>
        <CoursesList class="recent pb_120" :type="'recent'" :details="coursesDetails.recent" :cardsData="coursesCards.recent" />
        <Stats :statsData="stats" />
        <NewsLetter />
        <CoursesList class="popular pt_120 pb_70 mt-0" :type="'popular'" :details="coursesDetails.popular" :cardsData="coursesCards.popular" />
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
            },
            // Oggetto con contenuti esterni alle cards di Recent Courses e Popular Courses
            coursesDetails: {
                recent: {
                    title: 'Recent courses',
                    categories: ['all categories', 'art', 'exercise', 'material design', 'music', 'photography', 'software development'],
                    selected: 0
                },
                popular: {
                    title: 'Popular courses',
                    subtitle: 'Discover our most popular courses for self learning'
                }
            },
            // Oggetto con contenuti delle cards di Recent Courses e Popular Courses
            // Keys:
            //      -Attribute: inquadra se è una card normale o se ha l'attributo hot special etc, così da stampare la targhetta in alto a destra
            //      -Featured: per la targhetta in alto a sinistra diagonale, che viene stampata se featured è true
            //      -Image: src dell'immagine da stampare. Alcune immagini hanno jpeg, altre jpg altre png perciò scriverò anche la parte finale nella source
            //      -Category: categoria della card da stampare nel body della card
            //      -Description: descrizione della card da stampare nel suo body
            //      -Time/Rate: la card ha una o l'altra, stampa quella che ha true su "value". Poi prende il numero del voto/tempo da "amount"
            //      -Price: prezzo della card diviso in previous (per stampare lo sconto se previous non è null) e il prezzo attuale (current)
            // 
            // Ho scelto di scrivere anche il content di popular nonostante sia solo i primi 6 di recent, dato che è un array che può cambiare nel tempo e in questo modo si può modificare facilmente
            coursesCards: {
                recent: [
                    {   
                        attribute: 'normal',
                        featured: false,
                        image: 'photo-1461749280684-dccba630e2f6-272x161.jpeg',
                        category: 'apache',
                        description: 'Web Coding and Apache Basics',
                        time: {
                            value: true,
                            amount: 6
                        },
                        rate: {
                            value: false,
                            amount: null
                        },
                        price: {
                            previous: null,
                            current: 'free'
                        }
                    },
                    {   
                        attribute: 'new',
                        featured: true,
                        image: 'cat_2-272x161.jpg',
                        category: 'art',
                        description: 'Real Things Art Painting by Jason Ni',
                        time: {
                            value: true,
                            amount: 6
                        },
                        rate: {
                            value: false,
                            amount: null
                        },
                        price: {
                            previous: 60,
                            current: 45
                        }
                    },
                    {   
                        attribute: 'hot',
                        featured: false,
                        image: 'course-preview-272x161.jpg',
                        category: 'software development',
                        description: 'Basic of Masterstudy',
                        time: {
                            value: false,
                            amount: null
                        },
                        rate: {
                            value: true,
                            amount: 5
                        },
                        price: {
                            previous: null,
                            current: 'free'
                        }
                    },
                    {   
                        attribute: 'special',
                        featured: false,
                        image: 'photo-1496307042754-b4aa456c4a2d-272x161.jpeg',
                        category: 'electronic',
                        description: 'How to be a DJ? Make Electronic Music',
                        time: {
                            value: false,
                            amount: null
                        },
                        rate: {
                            value: true,
                            amount: 5
                        },
                        price: {
                            previous: 59,
                            current: 49
                        }
                    },
                    {   
                        attribute: 'normal',
                        featured: false,
                        image: 'photo-1416339134316-0e91dc9ded92-scaled-272x161.jpeg',
                        category: 'communication',
                        description: 'Design Instruments for Communication',
                        time: {
                            value: true,
                            amount: 6
                        },
                        rate: {
                            value: false,
                            amount: null
                        },
                        price: {
                            previous: null,
                            current: null
                        }
                    },
                    {   
                        attribute: 'normal',
                        featured: false,
                        image: 'cathryn-lavery-67852-unsplash-272x161.jpg',
                        category: 'art',
                        description: 'Make your Concept Right and Beautiful',
                        time: {
                            value: true,
                            amount: 6
                        },
                        rate: {
                            value: false,
                            amount: null
                        },
                        price: {
                            previous: null,
                            current: 70
                        }
                    },
                    {   
                        attribute: 'normal',
                        featured: false,
                        image: 'photo-1475452779376-caebfb988090-272x161.jpeg',
                        category: 'bicycling',
                        description: 'Road Bike Manual or How to Be a Champion.',
                        time: {
                            value: true,
                            amount: 6
                        },
                        rate: {
                            value: false,
                            amount: null
                        },
                        price: {
                            previous: null,
                            current: 20
                        }
                    },
                    {   
                        attribute: 'normal',
                        featured: false,
                        image: 'cristian-grecu-762012-unsplash-min-scaled-272x161.jpg',
                        category: 'documentary',
                        description: 'How to Make Beautiful Landscape photos?',
                        time: {
                            value: true,
                            amount: 6
                        },
                        rate: {
                            value: false,
                            amount: null
                        },
                        price: {
                            previous: null,
                            current: 60
                        }
                    },
                    {   
                        attribute: 'normal',
                        featured: false,
                        image: 'landscape-272x161.jpg',
                        category: 'art',
                        description: 'Let\'s paint Van Gogh\'s Starry Night',
                        time: {
                            value: true,
                            amount: 6
                        },
                        rate: {
                            value: false,
                            amount: null
                        },
                        price: {
                            previous: null,
                            current: 79
                        }
                    },
                    {   
                        attribute: 'special',
                        featured: false,
                        image: '12345-1-272x161.png',
                        category: 'nvidia',
                        description: 'Nvidia and UE4 Technologies Practice',
                        time: {
                            value: false,
                            amount: null
                        },
                        rate: {
                            value: true,
                            amount: 5
                        },
                        price: {
                            previous: null,
                            current: 'free'
                        }
                    },
                    {   
                        attribute: 'special',
                        featured: false,
                        image: 'jakob-owens-198234-unsplash-min-1-272x161.png',
                        category: 'art',
                        description: 'How to Work with Legendary RED camera?',
                        time: {
                            value: true,
                            amount: 6
                        },
                        rate: {
                            value: false,
                            amount: null
                        },
                        price: {
                            previous: null,
                            current: 'free'
                        }
                    },
                    {   
                        attribute: 'normal',
                        featured: false,
                        image: 'promo_tf-272x161.jpg',
                        category: 'software development',
                        description: 'MasterStudy Mobile LMS App',
                        time: {
                            value: true,
                            amount: 2
                        },
                        rate: {
                            value: false,
                            amount: null
                        },
                        price: {
                            previous: null,
                            current: 'free'
                        }
                    }
                ],
                popular: [
                    {   
                        attribute: 'normal',
                        featured: false,
                        image: 'photo-1461749280684-dccba630e2f6-272x161.jpeg',
                        category: 'apache',
                        description: 'Web Coding and Apache Basics',
                        time: {
                            value: true,
                            amount: 6
                        },
                        rate: {
                            value: false,
                            amount: null
                        },
                        price: {
                            previous: null,
                            current: 'free'
                        }
                    },
                    {   
                        attribute: 'new',
                        featured: true,
                        image: 'cat_2-272x161.jpg',
                        category: 'art',
                        description: 'Real Things Art Painting by Jason Ni',
                        time: {
                            value: true,
                            amount: 6
                        },
                        rate: {
                            value: false,
                            amount: null
                        },
                        price: {
                            previous: 60,
                            current: 45
                        }
                    },
                    {   
                        attribute: 'hot',
                        featured: false,
                        image: 'course-preview-272x161.jpg',
                        category: 'software development',
                        description: 'Basic of Masterstudy',
                        time: {
                            value: false,
                            amount: null
                        },
                        rate: {
                            value: true,
                            amount: 5
                        },
                        price: {
                            previous: null,
                            current: 'free'
                        }
                    },
                    {   
                        attribute: 'special',
                        featured: false,
                        image: 'photo-1496307042754-b4aa456c4a2d-272x161.jpeg',
                        category: 'electronic',
                        description: 'How to be a DJ? Make Electronic Music',
                        time: {
                            value: false,
                            amount: null
                        },
                        rate: {
                            value: true,
                            amount: 5
                        },
                        price: {
                            previous: 59,
                            current: 49
                        }
                    },
                    {   
                        attribute: 'normal',
                        featured: false,
                        image: 'photo-1416339134316-0e91dc9ded92-scaled-272x161.jpeg',
                        category: 'communication',
                        description: 'Design Instruments for Communication',
                        time: {
                            value: true,
                            amount: 6
                        },
                        rate: {
                            value: false,
                            amount: null
                        },
                        price: {
                            previous: null,
                            current: null
                        }
                    },
                    {   
                        attribute: 'normal',
                        featured: false,
                        image: 'cathryn-lavery-67852-unsplash-272x161.jpg',
                        category: 'art',
                        description: 'Make your Concept Right and Beautiful',
                        time: {
                            value: true,
                            amount: 6
                        },
                        rate: {
                            value: false,
                            amount: null
                        },
                        price: {
                            previous: null,
                            current: 70
                        }
                    },
                ]
            },
            // Array con i testi per la sezione stats
            stats: [
                {
                    amount: 2000,
                    item: 'students'
                },
                {
                    amount: 950,
                    item: 'courses'
                },
                {
                    amount: 1600,
                    item: 'hours video'
                },
                {
                    amount: 150,
                    item: 'countries reached'
                }
            ]
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
        .courses_list.popular{
            background-color: #f0f4fa;
        }
    }
</style>