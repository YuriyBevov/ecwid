<template>
    <nav class="nav" :class="showNav ? 'opened' : null">
        <div class="cmn__wrapper">
            <ul class="nav__list">
                <router-link to="#" class="cmn__link nav__link">Пряжа</router-link>
                <router-link to="#" class="cmn__link nav__link">Спицы</router-link>
                <router-link to="#" class="cmn__link nav__link">Крючки</router-link>
                <router-link to="#" class="cmn__link nav__link">Аксессуары</router-link>
                <router-link to="#" class="cmn__link nav__link">Подарочные сертификаты</router-link>
                <router-link to="#" class="cmn__link nav__link">МК и описания</router-link>
                <router-link to="#" class="cmn__link nav__link">Модели</router-link>
            </ul>

            <div class="nav__info">
                <Info/>
            </div>
        </div>    
    </nav>
</template>

<script>

    import Info from '@/components/Info.vue'

    export default {
        name: 'Nav',

        components: {
            Info
        },

        props: {
            isNavOpened: {type: Boolean}
        },

        data() {
            return {
                showNav: false,
            }
        },

        watch: {
            isNavOpened: function(newVal, oldVal) {
                !!newVal ? this.showNav = true : this.showNav = false
            }
        } 
    }

</script>



<style lang="scss" >
    @import '@/assets/styles/variables.scss';

    .nav {
        background-color: $col_green;
      
        &__list {
            display: flex;
            flex-wrap: wrap;
            max-width: 90rem;
            margin: 0 auto;

            @media(max-width: $tablet) {
                flex-direction: column;
            }
        }

        &__link {
            margin: 0 1rem;
            padding: 1rem;

            @media(max-width: $tablet_lg) {
                margin: 0 0.5rem;
                padding: 0.3rem;
            }
        }

        &__info {
            display: none;

            @media(max-width: $tablet) {
                display: flex;
                padding: 1rem;
            }
        }

        @media(max-width: $tablet) {
            display: none;

            &.opened {
                display: flex;
            }

            .info__list {
                padding-top: 2rem;
            }

            .info__item {
                display: flex;
                margin-bottom: 1rem;

                img {
                    display: none;
                }

                span, 
                a, 
                td {
                    color: $col_white;
                    text-align: center;
                }
            }
           
        }

    }
</style>