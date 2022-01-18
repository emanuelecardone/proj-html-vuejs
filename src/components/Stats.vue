<template>
    <section class="stats">
        <div class="container">
            <div class="row flex-column">
                <div class="offset-3 col-6">
                    <div class="stats_titles_section w-100 text-center mb_100">
                        <h2 class="mb-4">We are Proud</h2>
                        <p>Certificate courses are instructed by highly educated and qualified instructors who hold doctoral and master's level degrees.</p>
                    </div>
                </div>
                <div class="col-12">
                    <div class="row row-cols-4">
                        <div class="col" v-for="stat,index in statsData" :key="index">
                            <div class="single_stat w-100 text-center pt-4 pb-2">
                                <span class="amount_text fs_50 d-block mb-0">{{stat.amount}}</span>
                                <span class="item_text fs_20 text-uppercase">{{stat.item}}</span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: 'Stats',
    props: {
        statsData: Array
    }    
}
</script>

<style lang="scss" scoped>
@import '../style/variables.scss';

    .stats{
        padding: 100px 0 250px;
        background-color: #f0f4fa;
        background-image: url('../assets/img/we_proud.png');
        background-repeat: no-repeat;
        background-size: 100% 50%;
        background-position-y: 100%;

        .col:not(.col:last-child){
            border-right: 1px solid $tertiary_color;
        }
        .single_stat{

            .amount_text{
                color: $primary_color;
            }
            .item_text{
                color: $tertiary_color;
            }
        }
    }
</style>