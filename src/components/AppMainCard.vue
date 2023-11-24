<script>
export default {
    props: {
        thumb: String,
        price: String,
        series: String,
        type: String,
    }
}
</script>

<template>
    <div class="card">
        <img :src="thumb" :alt="series">
        <p>{{ series }}</p>
        <p>{{ type }}</p>
        <p>{{ price }}</p>
    </div>
</template>

<style lang="scss" scoped>
@use "../style/partials/variables.scss" as*;
@use "../style/partials/mixin.scss" as*;


.card {
    color: white;
    height: 100%;
    padding: 15px;

    p {
        text-transform: uppercase;
        font-size: .8rem;
    }

    p:first-of-type {
        margin-top: 10px;
    }

    img {
        width: 100%;
        aspect-ratio: 1/1;
    }
}
</style>