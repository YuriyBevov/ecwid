<template>
    <header class="header">
        <div class="cmn__wrapper header__wrapper">
            
            <router-link to="/" class="header__logo">
                <img src="~@/assets/images/logo.png" alt="логотип" width="90" height="70">
            </router-link>

            <div class="header__info">
                <Info/>
            </div>

            <div class="header__action">
                <a href="#" aria-label="Корзина">
                    <img src="~@/assets/images/cart.png" alt="иконка карты" width="30" height="30">
                </a>

                <div class="header__burger" @click="isNavOpened = !isNavOpened">
                    <div class="header__burger-top"></div>
                    <div class="header__burger-middle"></div>
                    <div class="header__burger-bottom"></div>
                </div>
            </div>
        </div>

        <Nav 
            :isNavOpened=isNavOpened    
        />
        
    </header>
</template>

<script>
    import Nav from '@/components/Nav.vue'
    import Info from '@/components/Info.vue'

    export default {
        name: 'Header',

        components: {
            Nav,
            Info
        },

        data() {
            return {
                isNavOpened: false
            }
        }
    }
</script>

<style lang="scss" scoped>
    @import '@/assets/styles/variables.scss';

    .header {
        
        position: sticky;
        top: 0;
        background-color: $col_white;
        z-index: 10000;

        &__burger {
            display: none;

            @media(max-width: $tablet) {
                display: flex;
                width: 3rem;
                height: 3rem;
                align-items: center;
                justify-content: space-around;
                flex-direction: column;
                cursor: pointer;
                margin-left: 2rem;

                &-top,
                &-middle,
                &-bottom {
                    width: 100%;
                    height: 3px;
                    background-color: $col_green;
                }
            }
        }

        &__wrapper {
            display: flex;
            flex-wrap: wrap;
            padding-top: 3rem;
            padding-bottom: 1.7rem;
            position: relative;

            @media(max-width: $tablet) {
                padding-top: 1rem;
                padding-bottom: 1rem;
            }
        }

        &__logo {
            margin-right: 10rem;

            @media(max-width: $tablet_md) {
                margin-right: 5rem;
            }
        }

       &__info {
            display: flex;
            flex-wrap: wrap;
            flex-grow: 1;
            max-width: 86rem;
       }

        &__action {
            display: flex;
            align-items: center;
            margin-left: auto;

            a{
                display: block;
                width: 3rem;
                height: 3rem;
                opacity: 1;

                transition: opacity $transition-rules;

                &:hover,
                &:focus {
                    opacity: 0.8;
                }

                &:active {
                    opacity: 0.6;
                }
            }
        }
    }
</style>