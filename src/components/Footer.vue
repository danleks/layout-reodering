<template>
    <footer class="footerWrapper">
        <p>Created with love by Danleks</p>
    </footer>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
    .footerWrapper {
        width: 100%;
        padding: 12px;
        margin-top: 20px;
        background-image: linear-gradient(to bottom right, #9f64e7, #6960f4);
        text-align: center;
        color: #fff;

        @media(min-width: 768px) {
            padding: 35px;
        }
        & > p {
            text-transform: capitalize;
        }
    }
</style>
