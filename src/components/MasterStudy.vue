<template>
    <!-- La sezione MasterStudy è l'ultima prima del footer, ha una col-7 con uno sfondo di base, il riquadro bianco ha un effetto vignetta creato con 
    un secondo div triangle, il div è reso un triangolo col trucco di width/height 0 e la dimensione dei bordi (3 dei quali con colore trasparente) -->
    <section class="master_study w-100 d-flex align-items-center py_50">
        <div class="container">
            <div class="row">
                <div class="col-7">
                    <div class="master_box position-relative">
                        <h3 class="title">Come as you are</h3>
                        <p class="description my-5 fs_20">MasterStudy used is an excellent workshop whether you come as a counselor, advisor, administrator, or faculty member. I am going home empowered. I am looking forward to attending the On Course MasterStudy and the MasterStudy National Conference next year and facilitating the use of this excellent retention/student success course at my college.</p>
                        <span class="name text-capitalize fs_20 fw-bold d-block">tim sab</span>
                        <span class="profession text-capitalize">general developer, stylemix themes</span>
                        <!-- Triangolo per effetto vignetta -->
                        <div class="triangle position-absolute"></div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: 'MasterStudy'    
}
</script>

<style lang="scss" scoped>
@import '../style/variables.scss';

    .master_study{
        height: 700px;
        background-image: url('../assets/img/brooke-cagle-224821-unsplash-1-1920x700.jpg');
        background-size: 100% 100%;

        .master_box{
            padding: 70px $min_padding_x 100px;
            background-color: white;

            h3{
                font-size: 35px;
            }
            .title,
            .name,
            .profession{
                color: $primary_color;
            }
            .description{
                color: $tertiary_color;
            }
            .triangle{
                width: 0;
                height: 0;
                border: 30px solid transparent;
                border-left: 35px solid white;
                left: 99%;
                top: 50%;
                transform: translateY(-50%);
            }
        }
    }
</style>