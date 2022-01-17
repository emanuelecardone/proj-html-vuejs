<template>
    <nav class="navbar up justify-content-between align-items-center px_100">
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
        
        height: 80px;
        border-bottom: 3px solid #e4e8ed;

        a{
            color: $tertiary_color;
        }

        ul{
            display: flex;

            &.links_list{
            gap: 1.75rem;

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
                        left: 50%;
                    }
                }
            }
            &.socials_list{
                gap: 1rem;

                a{
                    color: $primary_color;
                }
            }
        }
    }
</style>