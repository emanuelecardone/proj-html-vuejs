<template>
    <nav class="navbar down justify-content-between align-items-center">
        <div class="container-fluid">
            <a class="navbar-brand me-0" href="#">
                <img src="../assets/img/MasterStudy_logo.svg" alt="Logo">
            </a>
            <div class="middle_section_1 flex-grow-1">
                <span class="text-uppercase mx-4 fs_15 d-flex align-items-center">
                    <i class="fas fa-bars me-1"></i>    
                    category
                </span>
                <input type="search" class="form-control form-control-lg rounded-0" placeholder="Search courses">
                <Button :type="'icon'" class="rounded-0 h-100 py-3 px-4" />
            </div>
            <div class="middle_section_2" id="navbarSupportedContent">
                <a href="#" class="nav-item me-1">
                    <i class="fas fa-bullhorn"></i>
                    Become an Instructor
                </a>
                <a href="#" class="nav-item ms-4">
                    <i class="fas fa-briefcase"></i>
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
        padding: 0 $min_padding_x;
        
        .container-fluid{
            gap: 4rem;

            > div{
                display: flex;
                justify-content: center;
                align-items: center;

                &.middle_section_1{
                    color: $tertiary_color;
                    
                    input{
                        background-color: #e4e8ed;
                        border: none;

                        &::placeholder{
                            color: $tertiary_color;
                            font-size: 15px;
                            font-weight: bold;
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
    }
</style>