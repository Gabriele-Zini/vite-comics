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
                <img class="logo" src="../img/dc-logo.png" alt="dc logo">
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



    header {
        @include mixin.flex(row, space-between, center);
        height: 100px;

        nav {
            height: 100%;
        }

        .logo {
            width: 4rem;
        }

        ul {
            @include mixin.flex(row, center, center);
            gap: 1rem;
            list-style: none;
            height: 100%;

            li {
                height: 100%;

            }

            a {
                text-decoration: none;
                text-transform: uppercase;
                color: rgb(30, 27, 27);
                font-weight: 900;
                font-size: .8rem;
                height: inherit;
                display: inline-block;
                @include mixin.flex(row, center, center);
                box-sizing: border-box;
                border-bottom: 5px solid transparent;


                &:hover {
                    color: variables.$primary_color;
                    border-bottom: 5px solid variables.$primary_color;
                }
            }
        }
    }
}
</style>