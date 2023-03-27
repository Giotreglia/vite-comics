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
                <img :src="getImagePath(item.image)" :alt="item.text">
                <span>{{ item.text }}</span>
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

    img {
        display: inline-block;
        height: 30%;
    }

    span {
        font-weight: 400;
        font-size: 20px;
    }
}
</style>