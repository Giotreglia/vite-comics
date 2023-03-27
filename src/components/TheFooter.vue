<script>
export default {
    name: "TheFooter",
    data() {
        return {
            footerLinksComics: [
                {
                    href: "#characters",
                    text: "Characters",
                },
                {
                    href: "#comics",
                    text: "Comics",
                },
                {
                    href: "#movies",
                    text: "Movies",
                },
                {
                    href: "#tv",
                    text: "Tv",
                },
                {
                    href: "#games",
                    text: "Games",
                },
                {
                    href: "#collectibles",
                    text: "Collectibles",
                },
                {
                    href: "#videos",
                    text: "Videos",
                },
                {
                    href: "#fans",
                    text: "Fans",
                },
                {
                    href: "#news",
                    text: "News",
                },
                {
                    href: "#shop",
                    text: "Shop",
                }
            ],
            footerLinksShop: [
                {
                    href: "#shopdc",
                    text: "Shop DC",
                },
                {
                    href: "#shopdccollectibles",
                    text: "Shop DC Collectibles",
                }
            ],
            footerLinksDc: [
                {
                    href: "#termsofuse",
                    text: "Terms Of Use",
                },
                {
                    href: "#privacypolicy",
                    text: "Privacy Policy (New)",
                },
                {
                    href: "#adchoices",
                    text: "Ad Choices",
                },
                {
                    href: "#advertising",
                    text: "Advertising",
                },
                {
                    href: "#jobs",
                    text: "Jobs",
                },
                {
                    href: "#subscriptions",
                    text: "Subscriptions",
                },
                {
                    href: "#talentworkshops",
                    text: "Talent Workshops",
                },
                {
                    href: "#cpsccertificates",
                    text: "CPSC Certificates",
                },
                {
                    href: "#ratings",
                    text: "Ratings",
                },
                {
                    href: "#shophelp",
                    text: "Shop Help",
                },
                {
                    href: "#contactus",
                    text: "Contact Us",
                },
            ],
            footerLinksSites: [
                {
                    href: "#dc",
                    text: "DC",
                },
                {
                    href: "#madmagazine",
                    text: "MAD Magazine",
                },
                {
                    href: "dckids",
                    text: "DC Kids",
                },
                {
                    href: "#dcuniverse",
                    text: "DC Universe",
                },
                {
                    href: "#dcpowervisa",
                    text: "DC Power Visa",
                },
            ],

        }
    },
}
</script>

<template>
    <footer>
        <img id="footer-logo" src="../assets/dc-logo-bg.png" alt="dc logo">

        <nav id="footer-nav-container" class="container container-xl">
            <div class="footer-left">
                <h4>DC COMICS</h4>
                <ul id="footer-nav-list" class="p-0 my-3">
                    <li class="nav-item" v-for="link in footerLinksComics"><a :href="link.href">{{ link.text }}</a></li>
                </ul>
                <h4>SHOP</h4>
                <ul id="footer-nav-list" class="p-0 my-3">
                    <li class="nav-item" v-for="link in footerLinksShop"><a :href="link.href">{{ link.text }}</a></li>
                </ul>
            </div>


            <div class="footer-center">
                <h4>DC</h4>
                <ul id="footer-nav-list" class="p-0 my-3">
                    <li class="nav-item" v-for="link in footerLinksDc"><a :href="link.href">{{ link.text }}</a></li>
                </ul>
            </div>


            <div class="footer-right">
                <h4>SITES</h4>
                <ul id="footer-nav-list" class="p-0 my-3">
                    <li class="nav-item" v-for="link in footerLinksSites"><a :href="link.href">{{ link.text }}</a></li>
                </ul>
            </div>
        </nav>

    </footer>
</template>

<style scoped lang="scss">
@use "../styles/partials/variables";
@use "../styles/partials/mixins";

footer {
    height: variables.$footer-height;
    background-image: url("../assets/footer-bg.jpg");
    background-size: cover;
    background-repeat: no-repeat;
    background-position: center;
    position: relative;
    overflow: hidden;

    #footer-nav-container {

        padding: 50px 0;
        display: flex;
        gap: 20px;

        h4 {
            color: white;
        }

    }
}

#footer-logo {
    position: absolute;
    left: 55%;
    top: -100px;
    height: 140%;
}





#footer-nav-list {
    display: flex;
    flex-direction: column;

    a {
        text-decoration: none;
        color: variables.$color-text-grey;

        &:hover {
            color: white;
            text-decoration: underline;
        }
    }
}
</style>