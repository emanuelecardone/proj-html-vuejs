<template>
    <!-- La card è divisa in 2 div, uno con l'immagine ed uno coi testi, i 2 div hanno stessa altezza e per questo mi occorre dare un'altezza fissa alla card -->
    <div class="courses_card">
        <!-- Immagine della card -->
        <div class="card_img position-relative">
            <img :src="require('../assets/img/' + infos.image)" :alt="'Immagine corso di ' + infos.category" class="w-100 h-100">
            <!-- Marchio che compare per le cards con new,hot o special -->
            <div v-if="infos.attribute !== 'normal'" class="type_mark position-absolute text-uppercase" :class="infos.attribute">
                {{infos.attribute}}
            </div>
            <!-- Marchio che compare solo per i "featured" -->
            <div v-if="infos.featured" class="featured_mark position-absolute text-uppercase">
                featured
            </div>
        </div>
        <!-- Testi della card -->
        <div class="card_infos d-flex flex-column justify-content-between position-relative" :class="{'featured': infos.featured}">
            <!-- Testi superiori -->
            <div class="card_infos_up">
                <!-- Categoria -->
                <span class="category_name text-capitalize mb-2">
                    {{infos.category}}
                    <i class="fas fa-chevron-right fs_10"></i>
                </span>
                <!-- Descrizione -->
                <span class="description">{{infos.description}}</span>
            </div>
            <hr class="position-absolute">
            <!-- Testi inferiori -->
            <div class="card_infos_down">
                <!-- I testi in fondo stampano il tempo oppure il voto a seconda di quale è presente, stampano anche il prezzo se non è null -->
                <div class="bottom_infos d-flex justify-content-between align-items-center position-relative">
                    <!-- Tempo -->
                    <span v-if="infos.time.value" class="bottom_left_text">
                        <i class="far fa-clock"></i>
                        {{infos.time.amount}} hours
                    </span>
                    <!-- Voto -->
                    <span v-else-if="infos.rate.value" class="bottom_left_text">
                        <RateStars :fullStars="infos.rate.amount" class="d-inline" />
                        {{infos.rate.amount}}
                    </span>
                    <!-- Prezzo originale (se presente) -->
                    <span v-if="infos.price.previous !== null" class="previous_price_text position-absolute">
                        ${{infos.price.previous}}
                    </span>
                    <!-- Prezzo attuale -->
                    <span v-if="infos.price.current !== null" class="bottom_right_text d-flex text-capitalize">
                        <span v-if="infos.price.current !== 'free'">$</span>
                        <span>{{infos.price.current}}</span>
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
    
    /* Altezza card */
    .courses_card{
        height: 400px;

        /* Div principali della card */
        > div{
            width: 100%;
            height: 50%;

            /* Div superiore (img) */
             &.card_img{
                overflow: hidden;

                /* Immagine */
                img{
                    z-index: 1000;
                }
                /* Marchio con il tipo */
                .type_mark{
                    top: .5rem;
                    right: .5rem;
                    padding: .25rem .5rem;
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
                /* Marchio featured */
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

            /* Div inferiore (testi) */
            &.card_infos{
                border: 1px solid $tertiary_color;
                border-top: none;
                padding: 1rem;

                /* Bordo per il div con featured */
                &.featured{
                    border: 1px solid #f09d28;
                    border-top: none;
                }
                /* Block per gli span (per il prezzo lo span col dollaro sarà elemento flex così da evitare questo block) */
                span{
                    display: block;

                    /* Varie modifiche agli span */
                    &.category_name{
                        font-size: 15px;
                        color: darken(#e4e8ed, 10%);
                    }
                    &.description{
                        font-size: 17.5px;
                        color: $primary_color;
                    }
                    &.bottom_left_text{
                        font-size: 15px;
                        color: $primary_color;
                    }
                    &.previous_price_text{
                        font-size: 15px;
                        color: darken(#e4e8ed, 10%);
                        text-decoration: line-through;
                        bottom: 1rem;
                        right: 0;
                    }
                    &.bottom_right_text{
                        font-size: 17.5px;
                        color: $primary_color;
                        font-weight: bold;
                    }
                }
                /* Horizontal rule messa a metà esatta del div dei testi */
                hr{
                    width: calc(100% - 1rem);
                    top: 50%;
                    transform: translateY(-50%);
                    color: darken(#e4e8ed, 40%);
                }
            }
        }
    }
</style>