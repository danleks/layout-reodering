<template>
    <section class="formWrapper">
        <form action="#">
            <input type="text" placeholder="Name" required>
            <input type="email" placeholder="Email" required>
            <button type="submit">Sign me up!</button>
        </form>
    </section>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
    .formWrapper {
        padding: 12px;
        margin-top: 20px;
        background-image: linear-gradient(to bottom right, #9f64e7, #6960f4);

        @media(min-width: 768px) {
            padding: 35px;
        }

        form {
            display: flex;
            //justify-content: space-between;

            input {
                flex: 1;
                width: 100px;
                padding: 8px;
                border: none;
            }

            button {
                display: inline-block;
                padding: 8px;
                border: none;
            }
        }
    }


</style>
