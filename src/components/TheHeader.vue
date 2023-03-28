<script>
export default {
    name: "TheHeader",
    data() {
        return {
            dropdown: true,
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
                <ul id="nav-list" class="m-0">
                    <li class="nav-item" v-for="link in navLinks"><a :href="link.href">{{ link.text.toLocaleUpperCase()
                    }}</a></li>
                </ul>
                <div id="dropdown-container">
                    <div @click="dropdown = !dropdown">
                        <button class="hamburger" v-if="dropdown"><i class="fa-solid fa-bars"></i></button>
                        <button class="hamburger" v-else><i class="fa-solid fa-xmark"></i></button>
                    </div>
                    <div id="dropdown" v-if="!dropdown">
                        <ul id="nav-list-dropdown" class="d-flex m-0">
                            <li class="nav-item" v-for="link in navLinks"><a :href="link.href">{{
                                link.text.toLocaleUpperCase()
                            }}</a></li>
                        </ul>
                    </div>
                </div>
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
        padding: 20px 0;

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
    display: none;

    .nav-item {
        position: relative;
        cursor: pointer;
        line-height: 60px;

        a {
            text-decoration: none;
            display: inline-block;
            line-height: 118px;
            color: black;
            transition: all 0.2s;

            &:hover {
                color: variables.$color-primary;
            }

            &::after {
                content: "";
                position: absolute;
                bottom: 0;
                left: -15%;
                height: 5px;
                width: 130%;
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


#dropdown {
    position: absolute;
    top: variables.$header-height;
    right: 0;
    z-index: 9999;
    text-align: right;
}

#close-dropdown {
    position: absolute;
    right: 80px;
    top: 40px;
    font-size: 30px;
}

#nav-list-dropdown {
    display: flex;
    flex-direction: column;
    list-style: none;
    gap: 10px;
    width: 50vw;
    overflow-y: auto;
    background-color: rgba(255, 255, 255, 0.95);
    padding: 50px;
    border-radius: 5px;

    a {
        text-decoration: none;
        color: black;
        font-weight: bold;
        font-size: 20px;
    }
}

.hamburger {
    color: black;
    font-size: 30px;
    border: 0;
    background-color: transparent;
}


@media all and (min-width: 992px) {
    #nav-list {
        display: flex;
    }

    #dropdown-container {
        display: none;
    }
}
</style>