<script>
export default {
    name: "Banner",
    data() {
        return {
            bannerItems: [
                {
                    text: 'Digital Comics',
                    image: 'buy-comics-digital-comics.png'
                },
                {
                    text: 'Dc Merchandise',
                    image: 'buy-comics-merchandise.png'
                },
                {
                    text: 'Subscription',
                    image: 'buy-comics-subscriptions.png'
                },
                {
                    text: 'Comic Shop Locator',
                    image: 'buy-comics-shop-locator.png'
                },
                {
                    text: 'Dc Power Visa',
                    image: 'buy-dc-power-visa.svg'
                },
            ]
        }
    },
    methods: {

        getImagePath: function (img) {
            return new URL(`../assets/${img}`, import.meta.url).href;
        },
    }
}
</script>

<template>
    <div id="banner">
        <div class="h-100 container container-xl d-flex justify-content-around align-items-center">
            <div class="banner-item d-flex align-items-center" v-for="item in bannerItems">
                <a href="#"><img :src="getImagePath(item.image)" :alt="item.text"></a>
                <span class="banner-text"><a href="#">{{ item.text }}</a></span>
            </div>
        </div>
    </div>
</template>

<style scoped lang="scss">
@use "../styles/partials/variables";
@use "../styles/partials/mixins";

#banner {
    height: 180px;
    background-color: variables.$color-primary;
}

.banner-item {
    color: white;
    gap: 20px;
    height: 100%;

    a {
        height: 100%;
        display: flex;
        align-items: center;


        img {
            display: inline-block;
            height: 30%;
        }

        &:hover {
            scale: 1.1;
        }


    }

    span {
        font-weight: 400;
        font-size: 20px;

        a {
            text-decoration: none;
            color: white;

            &:hover {
                scale: 1.1;
                color: variables.$color-secondary;
            }
        }
    }
}

.banner-text {
    display: none;
}

@media all and (min-width: 992px) {
    .banner-text {
        display: inline-block;
    }
}
</style>