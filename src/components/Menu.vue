<template>
    <nav class="navigation">
        <div @click="$emit('toggle-menu')" class="menu">
            <span class="burger">
                <i class="burger__item"></i>
            </span>
            <span>Menu</span>
        </div>
        <transition name="slide">
            <ul v-if="showMenu || menu" class="navigation__list">
                <li class="navigation__item">
                    <a href="#">Item 01</a>
                </li>
                <li class="navigation__item">
                    <a href="#">Item 02</a>
                </li>
                <li class="navigation__item">
                    <a href="#">Item 03</a>
                </li>
                <li class="navigation__item">
                    <a href="#">Item 04</a>
                </li>
                <li class="navigation__item">
                    <a href="#">Item 05</a>
                </li>
                <li class="navigation__item">
                    <a href="#">Item 06</a>
                </li>
                <li class="navigation__item navigation__item--social">
                    <a href="#">
                        <i class="fab fa-twitter"></i>
                    </a>
                </li>
                <li class="navigation__item navigation__item--social">
                    <a href="#">
                        <i class="fab fa-instagram"></i>
                    </a>
                </li>
                <li class="navigation__item navigation__item--social">
                    <a href="#">
                        <i class="fab fa-facebook-square"></i>
                    </a>
                </li>
                <li class="navigation__item navigation__item--social">
                    <a href="#">
                        <i class="fab fa-google-plus-g"></i>
                    </a>
                </li>

            </ul>
        </transition>
    </nav>
</template>

<script>
export default {

    data() {
        return {
            menu: null,
        }
    },

    props: {
        menuOn: {
            type: Boolean,
            required: true,
        }
    },

    computed: {
        showMenu() {
            return this.menu = this.menuOn;
        }
    },

    mounted() {
        // show menu when initially loading the page on vieports >= 1024px
        if (window.innerWidth >= 1024) {
            this.menu = true;
        }

        window.addEventListener('resize', () => {
            if (window.innerWidth >= 1024) {
                this.menu = true;
            } else {
                this.menu = false;
            }
        });
    }

}
</script>

<style lang="scss" scoped>
    .navigation {

        position: relative;
        color: #fff;
        cursor: pointer;

        @media (min-width: 1024px) {
            width: 100%;
            order: 1;
        }

        .menu {
            z-index: 3;
            position: relative;
            display: flex;
            justify-content: center;
            padding: 12px;
            align-items: center;
            background-image: linear-gradient(to bottom right, #9f64e7, #6960f4);

            @media(min-width: 1024px) {
                display: none;
            }

            .burger {
                display: inline-block;
                width: 20px;
                height: 24px;
                cursor: pointer;

                &__item {
                    position: relative;
                    display: inline-block;
                    width: 18px;
                    height: 2px;
                    background-color: #fff;

                    &::before,
                    &::after {
                        position: absolute;
                        left: 0;
                        content: '';
                        width: 18px;
                        height: 2px;
                        background-color: #fff;
                    }
                    &::before {
                        top: 6px;
                    }
                    &::after {
                        top: -6px;
                    }
                }
            }

            span:last-child {
                font-weight: bold;
            }
        }



        &__list {
            position: fixed;
            display: flex;
            flex-wrap: wrap;
            width: 100%;
            box-shadow: 0px 6px 10px rgba(0,0,0,.4);
            text-align: center;
            list-style: none;
            background-image: linear-gradient(to bottom right, #9f64e7, #6960f4);

            @media(min-width: 1024px) {
                flex-wrap: nowrap;
                position: unset;
            }
        }

        &__item {
            flex: 1 100%;

            @media(min-width: 768px) {
                flex: 1 50%;
            }

            a {
                &,
                &:link,
                &:visited {
                    display: block;
                    padding: 10px;
                    text-decoration: none;
                    color: #fff;
                }

                &:hover {
                    background-color: #9770be;
                }
            }

            &--social {
                flex: 1 25%;
            }
        }
    }

// SLIDING ANIMATION FOR MENU

.slide-enter-active,
.slide-leave-active {
  transition: all 0.3s cubic-bezier(0.250, 0.460, 0.450, 0.940);
}

.slide-enter, .slide-leave-to
 {
  opacity: 0;
  transform: translateY(-300px);

}
</style>
