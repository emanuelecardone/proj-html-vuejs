<template>
    <!-- La card è divisa in 2 div, uno con l'immagine ed uno coi testi, i 2 div hanno stessa altezza e per questo mi occorre dare un'altezza fissa alla card -->
    <div class="courses_card">
        <div class="card_img position-relative">
            <img :src="require('../assets/img/' + infos.image)" :alt="'Immagine corso di ' + infos.category" class="w-100 h-100">
            <div v-if="infos.attribute !== 'normal'" class="type_mark position-absolute text-uppercase" :class="infos.attribute">
                {{infos.attribute}}
            </div>
            <div v-if="infos.featured" class="featured_mark position-absolute text-uppercase">
                featured
            </div>
        </div>
        <div class="card_infos d-flex flex-column justify-content-between" :class="{'featured': infos.featured}">
            <div class="card_infos_up">
                <span class="category_name text-capitalize mb-2">
                    {{infos.category}}
                    <i class="fas fa-chevron-right fs_10"></i>
                </span>
                <span class="description">{{infos.description}}</span>
            </div>
            <div class="card_infos_down">
                <hr>
                <div class="bottom_infos d-flex justify-content-between align-items-center">
                    <span v-if="infos.time.value" class="bottom_left_text">
                        <i class="far fa-clock"></i>
                        {{infos.time.amount}} hours
                    </span>
                    <span v-else-if="infos.rate.value" class="bottom_left_text">
                        <RateStars :fullStars="infos.rate.amount" class="d-inline" />
                        {{infos.rate.amount}}
                    </span>
                    <span v-if="infos.price.current !== null" class="bottom_right_text text-capitalize">
                        {{infos.price.current}}
                    </span>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import RateStars from './RateStars.vue';

export default {
    name: 'Card',
    components: {
        RateStars
    },
    props: {
        infos: Object
    }    
}
</script>

<style lang="scss" scoped>
@import '../style/variables.scss';
    
    .courses_card{
        height: 350px;

        > div{
            width: 100%;
            height: 50%;

            &.card_img{
                overflow: hidden;

                img{
                    z-index: 1000;
                }
                .type_mark{
                    top: .5rem;
                    right: .5rem;
                    padding: .2rem .4rem;
                    border-radius: 5px;
                    font-size: 12px;
                    color: white;
                    z-index: 2000;

                    &.new{
                        background-color: #4bd7a8;
                    }
                    &.hot{
                        background-color: #fd0303;
                    }
                    &.special{
                        background-color: #f09d28;
                    }
                }
                .featured_mark{
                    color: white;
                    background-color: #f09d28;
                    padding: .3rem 5rem;
                    transform: rotate(315deg);
                    font-size: 10px;
                    top: 1.2rem;
                    left: -4.5rem;
                    z-index: 2000;
                }
            }

            &.card_infos{
                border: 1px solid $tertiary_color;
                padding: .5rem;

                &.featured{
                    border: 1px solid #f09d28;
                    border-top: none;
                }
                span{
                    display: block;

                    &.category_name{
                        font-size: 12px;
                        color: darken(#e4e8ed, 10%);
                    }
                    &.description{
                        font-size: 15px;
                        color: $primary_color;
                    }
                    &.bottom_left_text{
                        font-size: 12px;
                        color: $primary_color;
                    }
                    &.bottom_right_text{
                        font-size: 15px;
                        color: $primary_color;
                        font-weight: bold;
                    }
                }
                hr{
                    color: darken(#e4e8ed, 30%);
                }
            }
        }
    }
</style>