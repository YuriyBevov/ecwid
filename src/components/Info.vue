<template>
    <div class="info">
        <ul class="info__list">

            <li class="info__item">
                <img src="~@/assets/images/map-pin.png" alt="иконка карты" width="30" height="30">
        
                <address class="info__content info__content--address">
                    <span class="cmn__text cmn__text--med">м. Кропоткинская</span>
                    <span class="cmn__text cmn__text--med">Соймоновский проезд, д.7 с.1</span>
                </address>
            </li>
            <li class="info__item">
                <img src="~@/assets/images/clock.png" alt="время работы" width="35" height="30">
        
                <table class="info__content info__content--worktime">
                    <tr>
                        <td class="cmn__text cmn__text--med">Пн - Пт</td>
                        <td class="cmn__text cmn__text--med">11 - 20</td>
                    </tr>
                    <tr>
                        <td class="cmn__text cmn__text--med">Сб - Вск</td>
                        <td class="cmn__text cmn__text--med">11 - 18</td>
                    </tr>
                </table>
            </li>
            <li class="info__item">
                <img src="~@/assets/images/phone.png" alt="иконка телефона" width="30" height="30">
        
                <div class="info__content info__content--phone">
                    <a href="tel:+78000000000" class="cmn__text cmn__text--med">+7 800 000 00 00</a>
                    <a href="tel:+78000000000" class="cmn__text cmn__text--med">+7 800 000 00 00</a>
                </div>
            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        name: 'Info'
    }
</script>

<style lang="scss">
    @import '@/assets/styles/variables.scss';
    @import '@/assets/styles/mixins.scss';

    .info {
        display: flex;
        flex-grow: 1;

        &__list {
            display: flex;
            flex-wrap: wrap;
            flex-grow: 1;

            @media(max-width: $tablet) {
                flex-direction: column;
            }
        }

        &__item {
            display: flex;
            align-items: center;
            margin-right: auto;

            img {
                margin-right: 1.5rem;
            }

            @media(max-width: $tablet_md) {
                &:first-child {
                    width: 100%;
                    margin-bottom: 1.5rem;
                }
            }

            @media(max-width: $tablet) {
                display: none;
            }
        }

        &__content {
            display: flex;
            flex-direction: column;
            align-items: flex-start;

            &--address {
                font-style: normal;
            }

            &--worktime {
                width: 10.8rem;

                tr {
                    width: 100%;
                    display: flex;
                    justify-content: space-between;
                }

                td {
                    line-height: 1.3rem;
                }

            }

            &--phone {
                a {
                    @include link-hover();

                    @media(max-width: $tablet) {
                        &:first-child {
                            margin-right: 1rem;
                        }
                    }
                }
                
            }
        }
    }
</style>