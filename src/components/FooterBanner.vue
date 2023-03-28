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
                <h4 id="follow-claim">FOLLOW US</h4>
                <a class="social" href="https://www.facebook.com/" target="_blank"><img src="../assets/footer-facebook.png"
                        alt="logo facebook"></a>
                <a class="social" href="https://twitter.com/" target="_blank"><img src="../assets/footer-twitter.png"
                        alt="logo facebook"></a>
                <a class="social" href="https://www.youtube.com/" target="_blank"><img src="../assets/footer-youtube.png"
                        alt="logo facebook"></a>
                <a class="social" href="https://www.pinterest.it/" target="_blank"><img src="../assets/footer-pinterest.png"
                        alt="logo facebook"></a>
                <a class="social" href="https://www.pscp.tv/" target="_blank"><img src="../assets/footer-periscope.png"
                        alt="logo facebook"></a>
            </div>

        </div>
    </div>
</template>

<style scoped lang="scss">
@use "../styles/partials/variables" as *;

#footer-banner {
    background-color: $color-secondary;
    height: $header-height;

    h4 {
        color: $color-primary;
        margin-bottom: 0;
        margin-right: 10px;
        font-weight: bolder;

    }
}

#banner-btn {
    padding: 12px 20px;
    background-color: transparent;
    font-size: 12px;
    border: 2px solid $color-primary;
    transition: all 0.2s;

    &:hover {
        background-color: $color-text-grey;
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

#follow-claim {
    display: none;
}

@media all and (min-width: 768px) {
    #follow-claim {
        display: inline-block;
    }

    #banner-btn {
        font-size: 20px;
    }

}
</style>