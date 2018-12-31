<template>
    <section class="imageWrapper">
        <img src="http://lorempixel.com/568/320/sports" alt="">
    </section>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
    .imageWrapper {

        padding: 12px;
        margin-top: 20px;
        background-image: linear-gradient(to bottom right, #9f64e7, #6960f4);

        @media(min-width: 768px) {
            padding: 35px;
        }

        @media(min-width: 1024px) {
            order: 3;
        }

            img {
                width: 100%;
            }
    }
</style>
