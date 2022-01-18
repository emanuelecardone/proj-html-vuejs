<template>
    <section class="courses_list">
        <div class="container-fluid">
            <div class="row row-cols-1 flex-column">
                <div class="col">
                    <div class="titles_section w-100">

                    </div>
                </div>
                <div class="col">
                    <div class="links_section">

                    </div>
                </div>
                <div class="col">
                    <div class="row row-cols-6">

                    </div>
                </div>
            </div>
        </div>
    </section> 
</template>

<script>
export default {
    name: 'CoursesList',
    props: {
        type: String,
        cardsData: Array
    }
}
</script>

<style lang="scss" scoped>

</style>