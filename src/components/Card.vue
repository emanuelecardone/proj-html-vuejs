<template>
    <!-- La card è divisa in 2 div, uno con l'immagine ed uno coi testi, i 2 div hanno stessa altezza e per questo mi occorre dare un'altezza fissa alla card -->
    <div class="courses_card">
        <div class="card_img">
            <img :src="require('../assets/img/' + infos.image)" :alt="'Immagine corso di ' + infos.category" class="w-100 h-100">
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

            &.card_infos{
                border: 1px solid $tertiary_color;
                padding: .5rem;

                &.featured{
                    border: 1px solid #fecc4f;
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