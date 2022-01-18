<template>
    <section class="courses_list mt_100">
        <div class="container-fluid">
            <div class="row row-cols-1 flex-column gy-5">
                <div class="col">
                    <div class="titles_section w-100">
                        <h2 class="text-center">{{details.title}}</h2>
                    </div>
                </div>
                <div class="col">
                    <div v-if="type === 'recent'" class="links_section w-100 d-flex justify-content-center align-items-center">
                        <ul class="links_list p-0 d-flex justify-content-between align-items-center">
                            <li v-for="category,index in details.categories" :key="index">
                                <a class="single_category_link text-capitalize" href="#">{{category}}</a>
                            </li>
                        </ul>
                    </div>
                    <h5 v-else>test</h5>
                </div>
                <div class="col">
                    <div class="row row-cols-6 gy-5">
                        <div class="col" v-for="card,index in cardsData" :key="index">
                            <Card :infos="card" />
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section> 
</template>

<script>
import Card from './Card.vue';

export default {
    name: 'CoursesList',
    components: {
        Card
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

        .links_section{

            .links_list{
                gap: 1rem;

                .single_category_link{
                    color: $secondary_color;
                }
            }
        }
    }
</style>