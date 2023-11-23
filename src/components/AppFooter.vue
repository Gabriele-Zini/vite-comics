<script>
export default {
    data() {

    }
}
</script>

<template>
    <footer>
        <div class="top-footer"></div>
        <div class="bottom-footer"></div>
    </footer>
</template>


<style lang="scss" scoped>
@use "../style/partials/variables.scss";
@use "../style/partials/mixin.scss";

footer {
    background-image: url(../../public/img/footer-bg.jpg);
    
    .top-footer {
        background-image: url(../../public/img/dc-logo-bg.png);
        background-repeat: no-repeat;
        background-position: right bottom;
        min-height: 500px;
    }
    .bottom-footer{
        min-height: 100px;
        background-color:variables.$footer-color;
    }
}
</style>