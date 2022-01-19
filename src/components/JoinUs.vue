<template>
    <!-- La sezione JoinUs contiene 2 inviti ad unirsi ai vari corsi come istruttore etc, il contenuto da stampare
    è stato creato direttamente in questo componente data la poca mole di dati, si divide in 2 cols -->
    <section class="join_us">
        <div class="container-fluid">
            <div class="row row-cols-2 gx-4">
                <div class="col" v-for="content,index in contents" :key="index">
                    <div class="box w-100 d-flex py_70">
                        <div class="image_box h-100 mx_50">
                            <img :src="require('../assets/img/' + content.image + '.png')" alt="Immagine Join Us">
                        </div>
                        <div class="content_box py-4 d-flex flex-column align-items-start">
                            <h3 class="box_title">{{content.title}}</h3>
                            <p class="box_description mt-3 mb-4">{{content.description}}</p>
                            <Button :type="'text'" :text="content.btnText" />
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
import Button from './Button.vue';

export default {
    name: 'JoinUs',
    components: {
        Button
    },
    data: function(){
        return {
            // Contenuti dei due box
            contents: [
                {
                    image: 'image_box_1-221x231',
                    title: 'Become an Instructor',
                    description: 'Teach what you love. Masterstudy gives you the tools to create a course.',
                    btnText: 'start teaching'
                },
                {
                    image: 'image_box_2-234x231',
                    title: 'Setup For Business',
                    description: 'Get unlimited access to 2,500 of Udemy\'s top courses for your team.',
                    btnText: 'doing business'
                }
            ]
        };
    }    
}
</script>

<style lang="scss" scoped>
    @import '../style/variables.scss';

        .join_us{
            padding: 100px $min_padding_x;

            .box{
                border: 1px solid $tertiary_color;
                padding-right: $min_padding_x;

                .content_box{

                    h3{
                        font-size: 40px;
                    }
                    p{
                        font-size: 20px;
                        color: $tertiary_color;
                    }
                }
            }
        }
</style>