<script>
import AppSection from './AppSection.vue';
import AppMainCard from './AppMainCard.vue';
import AppJumbotron from './AppJumbotron.vue';
export default {
    components: {
        AppSection,
        AppMainCard,
        AppJumbotron,
    },
    data() {
        return {
            comics: [
                {
                    thumb: "https://www.coverbrowser.com/image/action-comics/1-1.jpg",
                    price: "$19.99",
                    series: "Action Comics",
                    type: "comic book"
                },
                {
                    thumb: "https://www.panini.it/media/catalog/product/cache/a5b5dd3adfe0d321084804c738f29601/M/1/M1BLLA015ISBN_0.jpg",
                    price: "$3.99",
                    series: "American Vampire 1976",
                    type: "comic book"
                },
                {
                    thumb: "https://media.wired.com/photos/593384dad80dd005b42b2817/master/w_2560%2Cc_limit/Aquaman-16.jpg",
                    price: "$16.99",
                    series: "Aquaman",
                    type: "graphic novel"
                },
                {
                    thumb: "https://d29xot63vimef3.cloudfront.net/image/batgirl/1-1.jpg",
                    price: "$2.99",
                    series: "Batgirl",
                    type: "comic book"
                },
                {
                    thumb: "https://static.posters.cz/image/750/locandine-film-in-plexiglass-batman-prowl-comic-cover-i69653.jpg",
                    price: "$3.99",
                    series: "Batman",
                    type: "comic book"
                },
                {
                    thumb: "https://static.wikia.nocookie.net/marvel_dc/images/5/50/Batman_Beyond_v.1_1.jpg",
                    price: "$2.99",
                    series: "Batman Beyond",
                    type: "comic book"
                },
                {
                    thumb: "https://static.wikia.nocookie.net/marvel_dc/images/0/0d/Batman_Superman_Vol_1_1.jpg",
                    price: "$3.99",
                    series: "Batman/Superman",
                    type: "comic book"
                },
                {
                    thumb: "https://static.wikia.nocookie.net/marvel_dc/images/c/cf/Batman_Superman_Annual_Vol_2_1.jpg",
                    price: "$4.99",
                    series: "Batman/Superman Annual",
                    type: "comic book"
                },
                {
                    thumb: "https://static.wikia.nocookie.net/marvel_dc/images/5/54/Batman_The_Joker_War_Zone_Vol_1_1.jpg",
                    price: "$5.99",
                    series: "Batman: The Joker War Zone",
                    type: "comic book"
                },
                {
                    thumb: "https://static.wikia.nocookie.net/marvel_dc/images/6/64/Batman_Three_Jokers_Collected.jpg",
                    price: "$6.99",
                    series: "Batman: Three Jokers",
                    type: "comic book"
                },
                {
                    thumb: "https://static.wikia.nocookie.net/marvel_dc/images/f/f8/Batman_White_Knight_Presents_Harley_Quinn_Vol_1_1.jpg",
                    price: "$4.99",
                    series: "Batman: White Knight Presents: Harley Quinn",
                    type: "comic book"
                },
                {
                    thumb: "https://static.wikia.nocookie.net/marvel_dc/images/c/c8/Catwoman_Vol_2_1.jpg",
                    price: "$16.99",
                    series: "Catwoman",
                    type: "graphic novel"
                }
            ]
        }
    }
}
</script>

<template>
    <main>
        <AppJumbotron />
        <div class="button-container">
            <button>current series</button>
        </div>
        <div class="row">
            <div class="col" v-for="comic in comics" :key="comic.id">
                <AppMainCard :thumb="comic.thumb" :price="comic.price" :type="comic.type" :series="comic.series" />
            </div>
        </div>
        <div class="load-more-container">
            <button>load more</button>
        </div>
        <AppSection />
    </main>
</template>

<style lang="scss" scoped>
@use "../style/partials/variables.scss";
@use "../style/partials/mixin.scss";

main {
    background-color: variables.$main-bg-color;

    button {
        border: 1px solid transparent;
        background-color: variables.$primary-color;
        padding: .8rem 1.5rem;
        text-transform: uppercase;
        color: white;
        font-weight: bolder;
        cursor: pointer;
        border: 3px solid transparent;
        &:hover {
                background-color: variables.$main-bg-color;
                border: 3px solid variables.$primary_color;
            }
    }

    .button-container {
        width: 70%;
        margin: 0 auto;

        button {
            cursor: pointer;
            position: relative;
            bottom: 25px;
        }
    }


    .row {
        @include mixin.flex(row, center, stretch);
        flex-wrap: wrap;
        width: 70%;
        margin: 0 auto;

        .col {
            width: calc(100% / 6);

        }
    }

    .load-more-container {
        @include mixin.flex(row, center, center);
        margin-bottom: 20px;
    }
}
</style>