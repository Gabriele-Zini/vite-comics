<script>
export default {
    data() {
        return {
            menuEl: [
                {
                    text: "characters",
                    href: ""
                },
                {
                    text: "comics",
                    href: ""
                },
                {
                    text: "movies",
                    href: ""
                },
                {
                    text: "TV",
                    href: ""
                },
                {
                    text: "games",
                    href: ""
                },
                {
                    text: "collectibles",
                    href: ""
                },
                {
                    text: "videos",
                    href: ""
                },
                {
                    text: "fans",
                    href: ""
                },
                {
                    text: "news",
                    href: ""
                },
                {
                    text: "shop",
                    href: ""
                },

            ]
        }
    }
}
</script>

<template>
    <div class="container">
        <header>
            <div>
                <img class="logo" src="../../public/img/dc-logo.png" alt="dc logo">
            </div>
            <nav>
                <ul>
                    <li v-for="item in menuEl" :key="item.text"><a :href="item.href">{{ item.text }}</a></li>
                </ul>
            </nav>
        </header>
    </div>
</template>

<style lang="scss" scoped>
@use "../style/partials/variables.scss";
@use "../style/partials/mixin.scss";

.container {
    margin: 0 auto;
    width: 70%;
    padding: 1rem 0;

    header {
        @include mixin.flex(row, space-between, center);
        height: 80px;

        .logo {
            width: 4rem;
        }

        ul {
            @include mixin.flex(row, center, center);
            gap: 1rem;
            list-style: none;

            a {
                text-decoration: none;
                text-transform: uppercase;
                color: rgb(30, 27, 27);
                font-weight: 900;
                font-size: .8rem;
            }
        }
    }
}
</style>