<template>
    <!-- La Navbar superiore ha una scelta per la lingua e due liste di links sulla destra. Prende le informazioni da stampare 
    tramite props in arrivo da App->Header -->
    <nav class="navbar up justify-content-between align-items-center">
        <div class="container-fluid">

            <a class="nav-item d-flex justify-content-center align-items-center" href="#">
                English
                <i class="fas fa-chevron-down fs_10 ms-2"></i>
            </a>

            <div class="right_section d-flex justify-content-center align-items-center">
                <!-- Links -->
                <ul class="links_list flex-row navbar-nav me-auto mb-2 mb-lg-0">
                    <li v-for="link,index in thisData.links" :key="index" class="nav-item position-relative">
                        <a class="nav-link text-capitalize" href="#">{{link}}</a>
                        <div v-if="thisData.newIndexes.includes(index)" class="new_item fs_10">
                            new
                        </div>
                    </li>
                </ul>
                <!-- Socials -->
                <ul class="socials_list flex-row navbar-nav ms-5 me-auto mb-2 mb-lg-0">
                    <li v-for="social,index in thisData.socials" :key="index" class="nav-item">
                        <a class="nav-link text-capitalize" href="#">
                            <i :class="'fab fa-' + social"></i>
                        </a>
                    </li>
                </ul>
            </div>
        </div>
    </nav>
</template>

<script>
export default {
    name: 'NavbarUp',
    props: {
        thisData: Object
    }    
}
</script>

<style lang="scss" scoped>
@import '../style/variables.scss';

    .navbar.up{
        
        height: 70px;
        border-bottom: 3px solid #e4e8ed;
        padding: 0 $min_padding_x;

        a{
            color: $tertiary_color;
        }

        ul{
            display: flex;

            &.links_list{
            gap: 1.5rem;

                li{

                    .new_item{
                        background-color: #fd0303;
                        color: white;
                        text-transform: uppercase;
                        border-radius: 5px;
                        border-bottom-left-radius: 0;
                        padding: .1rem .4rem;
                        position: absolute;
                        bottom: 80%;
                        left: 75%;
                    }
                }
            }
            &.socials_list{
                gap: .75rem;

                a{
                    color: $primary_color;
                }
            }
        }
    }
</style>