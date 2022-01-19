<template>
    <!-- La sezione CoursesList verrà stampata 2 volte ed essendo entrambe molto simili cambiano pochi dettagli (in base alla props type)
    Le altre 2 props sono il contenuto secondario come titoli etc, e il contenuto delle cards da stampare  -->
    <section class="courses_list mt_100">
        <div class="container-fluid">
            <div class="row row-cols-1 flex-column gy-5">
                <!-- Col titolo -->
                <div class="col">
                    <div class="titles_section w-100">
                        <h2 class="text-center">{{details.title}}</h2>
                        <h5 v-if="type === 'popular'" class="popular_subtitle text-center">{{details.subtitle}}</h5>
                    </div>
                </div>
                <!-- Col links -->
                <div v-if="type === 'recent'" class="col">
                    <div class="links_section w-100 d-flex justify-content-center align-items-center">
                        <ul class="links_list p-0 d-flex justify-content-between align-items-center">
                            <li v-for="category,index in details.categories" :key="index">
                                <a class="single_category_link text-capitalize" href="#" :class="{'selected': index === details.selected}">{{category}}</a>
                            </li>
                        </ul>
                    </div>
                </div>
                <!-- Col cards -->
                <div class="col">
                    <div class="row row-cols-6 gx-4 gy-5">
                        <div class="col" v-for="card,index in cardsData" :key="index">
                            <Card :infos="card" />
                        </div>
                    </div>
                </div>
                <!-- Col button/arrows -->
                <div class="col">
                    <div class="bottom_section d-flex justify-content-center align-items-center">
                        <Button v-if="type === 'recent'" :type="'text'" :text="'show all'" />
                        <div v-else class="arrows_wrapper d-flex">
                            <div class="arrows_wrapper_left">
                                <i class="fas fa-chevron-left"></i>
                            </div>
                            <div class="arrows_wrapper_right">
                                <i class="fas fa-chevron-right"></i>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section> 
</template>

<script>
import Card from './Card.vue';
import Button from './Button.vue';

export default {
    name: 'CoursesList',
    components: {
        Card,
        Button
    },
    props: {
        type: String,
        details: Object,
        cardsData: Array
    }
}
</script>

<style lang="scss" scoped>
@import '../style/variables.scss';

    .courses_list{
        padding-left: $min_padding_x;
        padding-right: $min_padding_x;

        .titles_section{

            h2{
                font-size: 50px;
            }
            .popular_subtitle{
                color: $tertiary_color;
            }
        }
        .links_section{

            .links_list{
                gap: 1rem;

                .single_category_link{
                    color: $secondary_color;

                    &.selected{
                        color: $tertiary_color;
                        background-color: #e4e8ed;
                        padding: .5rem 1rem;
                        border-radius: 50rem;
                    }
                }
            }
        }
        .arrows_wrapper{
            color: $tertiary_color;

            > div{
                border: 1px solid $tertiary_color;
                width: 50px;
                height: 50px;
                display: flex;
                justify-content: center;
                align-items: center;
                background-color: white;

                &:hover{
                    background-color: #457992;
                    color: white;
                    cursor: pointer;
                }
            }
        }
    }
</style>