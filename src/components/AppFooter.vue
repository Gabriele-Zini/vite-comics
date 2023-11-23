<script>
export default {
    data() {
        return {
            topFooterElems: [
                {
                    title: "dc comics",
                    links: ["characters", "comics", "movies", "TV", "games", "videos", "news"]
                },
                {
                    title: "shop",
                    links: ["characters", "comics"]
                },
                {
                    title: "dc",
                    links: ["characters", "comics", "movies", "TV", "games", "videos", "news", "ratings", "shop help", "subscriptions", "jobs", "advertising"]
                },
                {
                    title: "sites",
                    links: ["DC characters", "DC comics", "DC movies", "DC games", "DC videos"]
                },
            ]
        }
    }
}
</script>

<template>
    <footer>
        <div class="top-footer">
            <ul class="footer-elems-container">
                <li v-for="item in topFooterElems" :key="item">
                    <h3>{{ item.title }}
                    </h3>
                    <ul>
                        <li v-for="(link) in item.links" :key="link"><a href="">{{ link }}</a></li>
                    </ul>
                </li>
            </ul>
        </div>
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
        color: white;
        padding: 0 5rem;


        .footer-elems-container {
            @include mixin.flex(column, flex-start, flex-start);
            flex-wrap: wrap;
            height: 450px;
            width: 250px;
            list-style: none;
            padding-top: 3rem;
            gap: 1.5rem;

            h3 {
                text-transform: uppercase;
                text-align: left;
                margin-top: .3rem;
                margin-right: 1rem;
                margin-left: 1rem;
            }

            ul {
                list-style: none;
                margin-top: 1rem;
                margin-right: 1rem;
                margin-left: 1rem;

                li {
                    margin-top: .2rem;

                    a {
                        color: rgba(255, 255, 255, 0.549);
                        text-decoration: none;
                    }
                }
            }

        }
    }

    .bottom-footer {
        min-height: 100px;
        background-color: variables.$footer-color;
    }
}
</style>