<script>
export default {
    name: "TheFooter",
    props: {
        links: Array
    },
    data() {
        return {

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
                    <li class="nav-item" v-for="(link, i) in links" :key="i"><a :href="link.href">{{ link.text }}</a></li>
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
@use "../styles/partials/variables" as *;

footer {
    height: $footer-height;
    background-image: url("../assets/footer-bg.jpg");
    background-size: cover;
    background-repeat: no-repeat;
    background-position: center;
    position: relative;
    overflow: hidden;

    #footer-nav-container {

        padding: 50px 20px;
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
    top: -20%;
    height: 140%;
    z-index: 0;
}





#footer-nav-list {
    display: flex;
    flex-direction: column;
    z-index: 1;

    a {
        text-decoration: none;
        color: $color-text-grey;

        &:hover {
            color: white;
            text-decoration: underline;
        }
    }
}

@media all and (min-width: 576px) {
    #footer-nav-container {

        padding: 50px 20px;
    }
}
</style>