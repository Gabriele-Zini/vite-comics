<script>
export default {
    data() {
        return {
            topFooterElems: [
                {
                    title: "dc comics",
                    links: [
                        {
                            link: "characters",
                            href: ""
                        },
                        {
                            link: "comics",
                            href: ""
                        },
                        {
                            link: "movies",
                            href: ""
                        },
                        {
                            link: "TV",
                            href: ""
                        },
                        {
                            link: "games",
                            href: ""
                        },
                        {
                            link: "news",
                            href: ""
                        }],
                },
                {
                    title: "shop",
                    links: [
                        {
                            link: "games",
                            href: ""
                        },
                        {
                            link: "news",
                            href: ""
                        }],
                },
                {
                    title: "dc",
                    links: [
                        {
                            link: "characters",
                            href: ""
                        },
                        {
                            link: "comics",
                            href: ""
                        },
                        {
                            link: "movies",
                            href: ""
                        },
                        {
                            link: "TV",
                            href: ""
                        },
                        {
                            link: "jobs",
                            href: ""
                        },
                        {
                            link: "subscriptions",
                            href: ""
                        },
                        {
                            link: "CPSC certificates",
                            href: ""
                        },
                        {
                            link: "ratings",
                            href: ""
                        },
                        {
                            link: "games",
                            href: ""
                        },
                        {
                            link: "contact us",
                            href: ""
                        },
                        {
                            link: "news",
                            href: ""
                        }],
                },
                {
                    title: "sites",
                    links: [
                        {
                            link: "DC",
                            href: ""
                        },
                        {
                            link: "MAD magazine",
                            href: ""
                        },
                        {
                            link: "DC movies",
                            href: ""
                        },
                        {
                            link: "DC Universe",
                            href: ""
                        },
                        {
                            link: "DC games",
                            href: ""
                        },
                       ],
                },
            ],
            socialLinks: [
                {
                    socialImg: "footer-facebook.png",
                },
                {
                    socialImg: "footer-periscope.png",
                },
                {
                    socialImg: "footer-pinterest.png",
                },
                {
                    socialImg: "footer-twitter.png",
                },
                {
                    socialImg: "footer-youtube.png",
                },
            ]
        }
    },
    methods: {

        getImage(img) {
            return new URL(`../../public/img/${img}`, import.meta.url).href;
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
                        <li v-for="link in item.links" :key="link.link"><a :href="link.href" >{{ link.link }}</a></li>
                    </ul>
                </li>
            </ul>
        </div>
        <div class="bottom-footer">
            <div>
                <button>sign-up now!</button>
                <div>
                    <div>follow us</div>
                    <ul v-for="img in socialLinks" :key="img">
                        <li><a href=""><img :src="getImage(img.socialImg)" alt=""></a></li>
                    </ul>
                </div>
            </div>
        </div>
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
        min-height: 400px;
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
                        color: rgba(255, 255, 255, 0.389);
                        text-decoration: none;
                        text-transform: capitalize;
                        font-size: .9rem;

                        &:hover {
                            color: white;
                        }
                    }
                }
            }

        }
    }

    .bottom-footer {
        @include mixin.flex(row, space-between, center);
        min-height: 100px;
        background-color: variables.$footer-color;

        div:first-child {
            @include mixin.flex(row, space-between, center);
            margin: 0 auto;
            width: 70%;

            button {
                color: white;
                background-color: variables.$footer_color;
                border: 3px solid variables.$primary_color;
                padding: .8rem 1.5rem;
                text-transform: uppercase;
                font-weight: 900;
                font-size: 1.2rem;
                cursor: pointer;

                &:hover {
                    background-color: variables.$primary_color;
                }
            }

            div:first-of-type {
                @include mixin.flex(row, center, center);
                gap: 1.6rem;

                div {
                    text-transform: uppercase;
                    color: variables.$primary_color;
                    font-size: 1.3rem;
                    font-weight: 900;
                }

                ul {
                    list-style: none;
                }
            }
        }
    }
}
</style>