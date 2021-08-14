<template>
    <section class="features">
        <div class="cmn__wrapper features__wrapper">
            <ul 
                class="features__list"
            >
                <li 
                    class="features__item"
                    v-for="(feature, i) of featuresList"
                    :key="'feature_' + i"
                >
                    <img :src=feature.imgUrl :alt=feature.featureDesc :width=feature.imgWidth :height=feature.imgHeight>

                    <p class="cmn__text cmn__text--bold cmn__text--green">{{feature.featureDesc}}</p>
                </li>                                                               
            </ul>
        </div>
    </section>
</template>

<script>
    export default {
        data() {
            return {
                featuresList: [
                    {
                        imgUrl: require('@/assets/icons/icon-sheep.png'),
                        imgWidth: '100',
                        imgHeight: '80',
                        featureDesc: 'Только натуральный состав'
                    },

                    {
                        imgUrl: require('@/assets/icons/icon-star.png'),
                        imgWidth: '90',
                        imgHeight: '90',
                        featureDesc: 'Актуальное наличие на\xa0сайте'
                    },

                    {
                        imgUrl: require('@/assets/icons/icon-delivery.png'),
                        imgWidth: '132',
                        imgHeight: '80',
                        featureDesc: 'Быстрая отправка'
                    },
                    
                    {
                        imgUrl: require('@/assets/icons/icon-place.png'),
                        imgWidth: '90',
                        imgHeight: '90',
                        featureDesc: 'Удобное расположение'
                    },
                    
                    {
                        imgUrl: require('@/assets/icons/icon-manager.png'),
                        imgWidth: '72',
                        imgHeight: '90',
                        featureDesc: 'Помощь в\xa0подборе товаров'
                    },          

                ]
            }
        }
    }
</script>

<style lang="scss" scoped>
     @import '@/assets/styles/variables.scss';

    .features {
        padding: 3.5rem 0;

        @media(max-width: $tablet_md) {
            padding: 1.5rem 0;
        }

        &__list {
            display: flex;
            flex-wrap: wrap;
            width: 100%;

            @media(max-width: $tablet) {
                justify-content: center;
            }
        }

        &__item {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: space-around;
            width: calc(20% - 1rem);
            min-height: 15.4rem;
            margin: 0 0.5rem;

            @media(max-width: $tablet) {
                width: calc(100% / 3 - 1rem);
                margin-bottom: 1rem;
            }

            @media(max-width: $mobile_lg) {
                width: 100%;
            }

            p {               
                max-width: 12rem;
                padding: 0 1rem;
                text-align: center;
            }
        }
    }
</style>