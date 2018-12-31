<template>
    <section class="headingWrapper">
        <h1 class="headingWrapper__title">Hi, how are you doing ?</h1>
    </section>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
    .headingWrapper {

        padding: 12px;
        margin-top: 20px;
        background-image: linear-gradient(to bottom right, #9f64e7, #6960f4);
        text-align: center;
        color: #fff;

        @media(min-width: 768px) {
            padding: 35px;
        }

        @media(min-width: 1024px) {
            order: 2;
        }

        &__title {
            text-transform: capitalize;
        }
    }


</style>
