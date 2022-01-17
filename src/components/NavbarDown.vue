<template>
    <nav class="navbar down justify-content-between align-items-center px_100">
        <div class="container-fluid">
            <a class="navbar-brand" href="#">
                <img src="../assets/img/MasterStudy_logo.svg" alt="Logo">
            </a>
            <div class="middle_section_1 w_40">
                <i class="fas fa-bars me-1"></i>
                <span class="text-uppercase me-3 fs_15">category</span>
                <input type="search" class="form-control form-control-md h_40p rounded-0" placeholder="Search courses">
                <Button :type="'icon'" class="rounded-0" />
            </div>
            <div class="middle_section_2" id="navbarSupportedContent">
                <a href="#" class="nav-item me-4">
                    <i class="fas fa-bullhorn me-2"></i>
                    Become an Instructor
                </a>
                <a href="#" class="nav-item">
                    <i class="fas fa-briefcase me-2"></i>
                    For Enterprise
                </a>
            </div>
            <div class="right_section">
                <a href="#" class="nav-item">
                     <i class="fas fa-user"></i>
                    Log in
                </a>
                <Button :type="'text'" :text="'sign up'" class="mx-4" />
                <i class="far fa-bookmark fs-4"></i>
            </div>
        </div>
    </nav>
</template>

<script>
import Button from './Button.vue';

export default {
    name: 'NavbarDown',
    components: {
        Button
    }
}
</script>

<style lang="scss" scoped>
@import '../style/variables.scss';

    .navbar.down{

        height: 90px;
        
        .container-fluid{

            > div{
                display: flex;
                justify-content: center;
                align-items: center;

                &.middle_section_1{
                    color: $tertiary_color;
                    
                    input{
                        background-color: #e4e8ed;

                        &::placeholder{
                            color: $tertiary_color;
                        }
                    }
                }
                &.middle_section_2{
                    i{
                        color: $secondary_color;
                    }
                    a{
                        color: $primary_color;
                    }
                }
                &.right_section{
                    color: $secondary_color;
                }
            }
        }

        .btn{
            display: block;
            height: 40px;
            padding: 0 25px;
        }
    }
</style>