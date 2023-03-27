<script>
export default {
    name: "TheHeader",
    data() {
        return {
            navLinks: [
                {
                    href: "#characters",
                    text: "CHARACTERS",
                },
                {
                    href: "#comics",
                    text: "COMICS",
                },
                {
                    href: "#movies",
                    text: "MOVIES",
                },
                {
                    href: "#tv",
                    text: "TV",
                },
                {
                    href: "#games",
                    text: "GAMES",
                },
                {
                    href: "#collectibles",
                    text: "COLLECTIBLES",
                },
                {
                    href: "#videos",
                    text: "VIDEOS",
                },
                {
                    href: "#fans",
                    text: "FANS",
                },
                {
                    href: "#news",
                    text: "NEWS",
                },
                {
                    href: "#shop",
                    text: "SHOP",
                }
            ]
        }
    },
}
</script>

<template>
    <!-- Header -->
    <header>
        <div id="header-container" class="container container-xl">
            <div id="logo-container">
                <a href="#"><img src="../assets/dc-logo.png" alt="logo Dc"></a>
            </div>

            <nav>
                <ul id="nav-list" class="d-flex">
                    <li class="nav-item" v-for="link in navLinks"><a :href="link.href">{{ link.text.toLocaleUpperCase()
                    }}</a></li>
                </ul>
            </nav>

        </div>
    </header>
</template>


<style scoped lang="scss">
@use "../styles/partials/variables";
@use "../styles/partials/mixins";

#header-container {
    height: variables.$header-height;
    @include mixins.d-flex-space-between-center;

    #logo-container {
        height: 100%;
        padding: 20px;

        img {
            height: 100%;
            cursor: pointer;
        }
    }

}

#nav-list {
    list-style: none;
    gap: 20px;
    font-weight: bold;
    height: 100%;

    .nav-item {
        position: relative;
        cursor: pointer;
        line-height: 60px;

        a {
            text-decoration: none;
            display: inline-block;
            line-height: 60px;
            color: black;
            transition: all 0.2s;

            &:hover {
                color: variables.$color-primary;
            }

            &::after {
                content: "";
                position: absolute;
                bottom: -25px;
                left: 2px;
                height: 5px;
                width: 100%;
                background-color: variables.$color-primary;
                opacity: 0;
                transition: all 0.2s;
            }

            &:hover::after {
                opacity: 1;
            }
        }

    }
}
</style>