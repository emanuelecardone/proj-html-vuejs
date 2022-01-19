<template>
    <!-- Le col del footer non verranno ciclate in quanto ogni col ha un tipo di contenuto diverso dagli altri, quindi devo lavorare su ogni col singola
    Le informazioni (props data) da stampare in pagina saranno quindi divise in 4 sotto oggetti, ognuno diverso dall'altro in base al contenuto da stampare -->
    <footer class="pt_70 pb_50">
        <div class="container">
            <div class="row row-cols-4 gx-5">
                <!-- About -->
                <div class="col">
                    <div class="footer_box about">
                        <h5 class="title">{{data.about.name}}</h5>
                        <div class="content">   
                            <p class="mb-3">
                                <span class="evidence">{{data.about.text1Evidence}}</span> 
                                <span>{{data.about.text1}}</span> <br>
                                <span>{{data.about.text2}}</span> 
                                <span class="evidence">{{data.about.text2Evidence}}.</span>
                            </p>
                            <div class="about_icons d-flex">
                                <a v-for="icon,index in data.about.icons" :key="index"  href="#">
                                    <i :class="'fab fa-' + icon"></i>
                                </a>                                
                            </div>
                        </div>
                    </div>
                </div>
                <!-- Contact -->
                <div class="col">
                    <div class="footer_box contact">
                        <h5 class="title">{{data.contact.name}}</h5>
                        <div class="content">
                            <span>
                                {{data.contact.address}}
                            </span>
                            <div class="numbers">
                                <span v-for="number,index in data.contact.numberContacts" :key="index" class="d-block">
                                    {{number.name}}: {{number.number}}
                                </span>
                            </div>
                            <span class="email">{{data.contact.email}}</span>
                        </div>
                    </div>
                </div>
                <!-- Pages -->
                <div class="col">
                    <div class="footer_box pages">
                        <h5 class="title">{{data.pages.name}}</h5>
                        <div class="content w-100 d-flex justify-content-between">
                            <ul class="left">
                                <li v-for="page,index in data.pages.pagesNames.left" :key="index" class="text-capitalize mb-2">{{page}}</li>
                            </ul>
                            <ul class="right">
                                <li v-for="page,index in data.pages.pagesNames.right" :key="index" class="text-capitalize mb-2">{{page}}</li>
                            </ul>
                        </div>
                    </div>
                </div>
                <!-- Blog -->
                <div class="col">
                    <div class="footer_box blog">
                        <h5 class="title">{{data.blog.name}}</h5>
                        <div class="content w-100 d-flex flex-column">
                            <div v-for="blog,index in data.blog.blogs" :key="index" class="single_blog w-100 d-flex">
                                <img :src="require('../assets/img/' + blog.image + '.jpeg')" alt="Immagine blog" class="w_75p h_75p">
                                <div class="h-100 blog_text d-flex flex-column justify-content-between">
                                    <span class="main_text fw-bold">{{blog.text}}</span>
                                    <span class="sub_text">-- {{blog.date}}</span>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </footer>
</template>

<script>
export default {
    name: 'Footer',
    props: {
        data: Object
    }
}
</script>

<style lang="scss" scoped>
@import '../style/variables.scss';

    footer{

        /* Customizzazione delle 4 sezioni (col) */
        .footer_box{
            width: 100%;
            height: 100%;
            display: flex;
            flex-direction: column;
            align-items: flex-start;
            gap: 30px;

            .title{
                text-transform: capitalize;
                font-weight: bold;
            }

            &.about{
                color: $primary_color;
                .evidence{
                    color: $secondary_color;
                }
                .about_icons{
                    gap: 1rem;
                    color: $tertiary_color;

                    a{
                        color: inherit;
                    }
                }
            }
            &.contact{

                .content{
                    display: flex;
                    flex-direction: column;
                    gap: 1rem;  
                    color: $primary_color;
                    
                    .email{
                        color: $tertiary_color;
                    }
                }
            }
            &.pages{
                color: $primary_color;

                ul{
                    list-style-type: circle;
                    padding: 0;
                }
            }
            &.blog{

                .content{
                    gap: 1rem;

                    .single_blog{
                        gap: 1.5rem;

                        .blog_text{

                            span{
                                font-size: 13.5px;

                                &.main_text{
                                    color: $tertiary_color;
                                }
                                &.sub_text{
                                    color: darken(#e4e8ed, 5%);
                                }
                            }
                        }
                    }
                }
                
            }
        }
    }
</style>