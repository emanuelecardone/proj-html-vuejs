<template>
    <!-- Sezione NewsLetter: divisa in 2 col, la prima con dei testi e la seconda con una input email -->
    <section class="newsletter w-100">
        <div class="container">
            <div class="row">
                <div class="col-7">
                    <div class="text_section w-100">
                        <h5 class="fw-bold mb-3">Subscribe our newsletter</h5>
                        <p>There are many variations of passages of Lorem Ipsum available, but the majority have suffered alteration in some form, by injected humour, or randomised words</p>
                    </div>
                </div>
                <div class="col-5">
                    <div class="input_section w-100">
                        <h5 class="text-uppercase mb-3">your e-mail address</h5>
                        <div class="input_wrapper d-flex">
                            <input type="email" class="form-control form-control-lg rounded-0 border-0" placeholder="Enter your E-mail">
                            <Button :type="'text'" :text="'subscribe'" class="rounded-0" />
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
    name: 'NewsLetter',
    components: {
        Button
    }    
}
</script>

<style lang="scss" scoped>
@import '../style/variables.scss';

    .newsletter{
        background-color: #4bd7a8;
        padding: 75px 0;
        color: white;

        input::placeholder{
            font-size: 17.5px;
            color: $tertiary_color;
        }
    }
</style>