<script>
export default {
    name: "Grid",
    props: {
        cards: Array
    },
    data() {
        return {
        }
    },
    methods: {

        getImagePath: function (img) {
            return new URL(img, import.meta.url).href;
        },
    }
}
</script>

<template>
    <div id="card-container" class="container container-xl d-flex">
        <div class="my-card" v-for="(card, i) in cards" :key="i">
            <div class="image-wrapper">
                <img :src="getImagePath(card.thumb)">
            </div>
            <span class="card-title">{{ card.series }}</span>
        </div>
    </div>
</template>

<style scoped lang="scss">
@use "../styles/partials/variables" as *;

#card-container {
    flex-wrap: wrap;
    padding: 40px 10px;
}

.my-card {
    width: calc(100% / 2);
    height: 280px;
    padding: 10px;
    cursor: pointer;

    .image-wrapper {
        height: 80%;
        width: 100%;
        overflow: hidden;

        img {
            width: 100%;
            object-fit: cover;
            transition: all 2s;
        }

        &:hover {
            scale: 1.02;
        }

        &:active {
            scale: 1;
        }
    }

    .card-title {
        color: white;
        text-transform: uppercase;
        margin-top: 20px;
        display: inline-block;
        font-size: 18px;
    }

}


@media all and (min-width: 768px) {
    .my-card {
        width: calc(100% / 3);
    }
}

@media all and (min-width: 992px) {
    .my-card {
        width: calc(100% / 4);
    }
}

@media all and (min-width: 1400px) {
    .my-card {
        width: calc(100% / 6);
    }
}
</style>