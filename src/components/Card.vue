<template>
    <!-- La card è divisa in 2 div, uno con l'immagine ed uno coi testi, i 2 div hanno stessa altezza e per questo mi occorre dare un'altezza fissa alla card -->
    <div class="courses_card h_200p">
        <div class="card_img">
            test up
        </div>
        <div class="card_infos" :class="{'featured': infos.featured}">
            test down
        </div>
    </div>
</template>

<script>
export default {
    name: 'Card',
    props: {
        infos: Object
    }    
}
</script>

<style lang="scss" scoped>
@import '../style/variables.scss';
    
    .courses_card{

        > div{
            width: 100%;
            height: 50%;
            border: 1px solid $tertiary_color;

            &.featured{
                border: 1px solid #fecc4f;
                border-top: none;
            }
        }
    }
</style>