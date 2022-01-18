<template>
    <!-- Questo toolsbox sarà sempre presente a 50vh di altezza con position fixed -->
    <div class="toolsbox d-flex flex-column justify-content-between align-items-center p-4">
        <i v-for="icon,index in icons" :key="index" :class="'tool_icon fas fa-' + icon"></i>
    </div>
</template>

<script>
export default {
    name: 'ToolsBox',
    data: function(){
        return {
            // Classi delle icone font awesome
            icons: ['desktop', 'dharmachakra', 'wrench', 'shopping-cart', 'mobile-alt']
        };
    }    
}
</script>

<style lang="scss" scoped>
@import '../style/variables.scss';

    .toolsbox{
        position: fixed;
        right: 0;
        top: calc(50vh - 60px);
        box-shadow: -2.5px 5px 10px 1px $primary_color;
        width: 60px;
        height: 250px;
        z-index: 3500;
        background-color: white;

        .tool_icon{
            font-size: 20px;
            color: $primary_color;
        }
    }
</style>