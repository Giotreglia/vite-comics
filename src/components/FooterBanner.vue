<script>
export default {
    name: "FooterBanner",
    data() {
        return {
        }
    }
}
</script>

<template>
    <div id="footer-banner">
        <div id="footer-banner-container"
            class="h-100 container container-xl d-flex justify-content-between align-items-center">
            <div class="h-100 d-flex align-items-center">
                <button id="banner-btn"><a href="#">SIGN-UP NOW!</a></button>
            </div>

            <div class="h-100 d-flex align-items-center">
                <h4>FOLLOW US</h4>
                <a class="social" href="#"><img src="../assets/footer-facebook.png" alt="logo facebook"></a>
                <a class="social" href="#"><img src="../assets/footer-twitter.png" alt="logo facebook"></a>
                <a class="social" href="#"><img src="../assets/footer-youtube.png" alt="logo facebook"></a>
                <a class="social" href="#"><img src="../assets/footer-pinterest.png" alt="logo facebook"></a>
                <a class="social" href="#"><img src="../assets/footer-periscope.png" alt="logo facebook"></a>
            </div>

        </div>
    </div>
</template>

<style scoped lang="scss">
@use "../styles/partials/variables";
@use "../styles/partials/mixins";

#footer-banner {
    background-color: variables.$color-secondary;
    height: variables.$header-height;

    h4 {
        color: variables.$color-primary;
        margin-bottom: 0;
        margin-right: 10px;
        font-weight: bolder;

    }
}

#banner-btn {
    padding: 12px 20px;
    background-color: transparent;
    font-size: 20px;
    border: 2px solid variables.$color-primary;
    transition: all 0.2s;

    &:hover {
        background-color: variables.$color-text-grey;
    }

    &:active {
        scale: 0.95;
    }

    a {
        text-decoration: none;
        color: white;
    }

}

.social {
    display: inline-block;
    margin: 10px;

    &:hover {
        scale: 1.1;
        background-color: white;
        border-radius: 50%;
    }
}
</style>