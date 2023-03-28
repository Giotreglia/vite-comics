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
        <div id="label">Current series</div>
        <div class="my-card" v-for="(card, i) in cards" :key="i">
            <div class="image-wrapper">
                <img :src="getImagePath(card.thumb)">
            </div>
            <span class="card-title">{{ card.series }}</span>
        </div>
        <button id="load-more"><a href="#">Load More</a></button>
    </div>
</template>

<style scoped lang="scss">
@use "../styles/partials/variables" as *;

#card-container {
    flex-wrap: wrap;
    padding: 40px 10px;
    position: relative;
}

#label {
    position: absolute;
    top: -25px;
    background-color: $color-primary;
    color: white;
    padding: 5px 20px;
    font-size: 25px;
    text-transform: uppercase;
}

#load-more {
    padding: 8px 60px;
    border: 0;
    margin: 70px auto 0;
    font-size: 25px;
    text-transform: uppercase;
    background-color: $color-primary;
    transition: all 0.2s;

    &:hover {
        scale: 1.05;
        background-color: lighten($color-primary, 20);
    }

    &:active {
        scale: 1;
    }

    a {
        text-decoration: none;
        color: white;
        font-weight: bold;
    }
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
            box-shadow: 2px 2px 15px 2px rgba(255, 255, 255, 0.384);
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