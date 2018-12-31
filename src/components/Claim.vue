<template>
    <section class="claimWrapper">
        <p>We are very glad to see you here! Join us :)</p>
    </section>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
    .claimWrapper {
        padding: 12px;
        margin-top: 20px;
        background-image: linear-gradient(to bottom right, #9f64e7, #6960f4);
        text-align: center;
        color: #fff;

        @media(min-width: 768px) {
            padding: 35px;
        }

        & > h1 {
            text-transform: capitalize;
        }
    }
</style>
