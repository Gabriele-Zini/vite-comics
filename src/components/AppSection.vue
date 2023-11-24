<script>
export default {
    data() {
        return {
            dcElems: [
                {
                    text: "digital comics",
                    img: "buy-comics-digital-comics.png"
                },
                {
                    text: "dc merchandise",
                    img: "buy-comics-merchandise.png"
                },
                {
                    text: "subscription",
                    img: "buy-comics-subscriptions.png"
                },
                {
                    text: "comic shop locator",
                    img: "buy-comics-shop-locator.png"
                },
                {
                    text: "dc power visa",
                    img: "buy-dc-power-visa.svg"
                },
            ]
        }
    },
    methods: {
        getImage(img) {
            return new URL(`../img/${img}`, import.meta.url).href;
        }
    }
}
</script>

<template>
    <section>
        <div class="row">
            <div class="card" v-for="item of dcElems" :key="item">
                <img :src="getImage(item.img)" alt="">
                <div><a class="text-img" href="">{{ item.text }}</a></div>
            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped>
@use "../style/partials/variables.scss";
@use "../style/partials/mixin.scss";

section {
    background-color: variables.$primary_color;
    min-height: 200px;
    @include mixin.flex(row, center, center);
    gap: 2rem;

    .row {
        @include mixin.flex(row, center, center);
        gap: 2.2rem;

        .card {
            @include mixin.flex(row, center, center);
            gap: .8rem;


            .text-img {
                color: white;
                text-transform: uppercase;
                text-decoration: none;

                &:hover {
                    color: black;
                }
            }

            img {
                width: 3rem;
            }
        }
    }
}
</style>