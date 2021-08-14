<template>
    <section class="gallery">
        <div class="cmn__wrapper gallery__wrapper">
            <div class="slider">

                <div class="slider__container">
                
                    <div 
                        class="slider__slide"
                        v-for="(slide, i) of slideList"
                        :key="'slide_' + i"
                        :class="sliderOptions.current === i ? 'active' : null"
                    >
                        <img :src=slide.imgUrl :alt=slide.alt class="js-ofi-polyfill">
                    </div>

                    <div 
                        class="slider__pagination"
                    >
                        <button class="slider__pagination-item" aria-label="элемент пагинации"
                            v-for="(pag,i) of slideList"
                            :key="'pag_' + i"
                            :class="sliderOptions.current === i ? 'active' : null" 
                            @click="onClickChangeSlide(i)"                           
                        />
                    </div>

                    <div class="slider__navigation">
                        <button class="slider-btn-next" @click="onClickShowNextSlide">
                            <img src="~@/assets/icons/icon-arr.svg" alt="вперед">
                        </button>

                        <button class="slider-btn-prev" @click="onClickShowPrevSlide">
                            <img src="~@/assets/icons/icon-arr.svg" alt="назад">
                        </button>
                    </div>

                </div>
            </div>
        </div>
    </section>
</template>

<script>
    export default {
        data() {
            return {
                slideList: [
                    {
                        imgUrl: require('@/assets/images/slide_1.png'),
                        alt: 'слайд_1'
                    },

                    {
                        imgUrl: require('@/assets/images/slide_2.png'),
                        alt: 'слайд_2'
                    },
                    {
                        imgUrl: require('@/assets/images/slide_1.png'),
                        alt: 'слайд_1'
                    },

                    {
                        imgUrl: require('@/assets/images/slide_2.png'),
                        alt: 'слайд_2'
                    },                                        
                    {
                        imgUrl: require('@/assets/images/slide_1.png'),
                        alt: 'слайд_1'
                    }
                ],
            
                sliderOptions: {
                    current: 0
                }
            }
        },

        methods: {
            onClickShowNextSlide() {
                this.sliderOptions.current !== this.slideList.length - 1 ?
                this.sliderOptions.current += 1 :
                this.sliderOptions.current = 0
            },

            onClickShowPrevSlide() {
                this.sliderOptions.current !== 0 ?
                this.sliderOptions.current -= 1 :
                this.sliderOptions.current = this.slideList.length - 1
            },

            onClickChangeSlide(index) {
                this.sliderOptions.current = index
            }
        }
    }
</script>

<style lang="scss">
    @import '@/assets/styles/variables.scss';
    .gallery {
        padding: 3.5rem 0;
    }

    .slider {
        &__container {
            position: relative;
            display: flex;
            flex-wrap: nowrap;
            width: 100%;
            max-width: 111rem;
            height: 40rem;
            overflow: hidden;

            @media(max-width: $tablet_md) {
                height: 30rem;
            }

            @media(max-width: $tablet) {
                height: 25rem;
            }

            @media(max-width: $mobile_lg) {
                height: 20rem;
            }
        }

        &__slide {
            position: absolute;
            top: 0;
            left: 0;

            width: 100%;
            height: 100%;
            z-index: -1;
            opacity: 0;

            transition: opacity $transition-rules;
            
            img {
                display: block;
                width: 100%;
                height: 100%;
                object-fit: cover;
            }

            &.active {
                opacity: 1;
                z-index: 10;
            }
        }

        &__pagination {
            position: absolute;

            bottom: 1rem;
            left: 50%;

            transform: translateX(-50%);

            cursor: pointer;
            z-index: 100;

            @media(max-width: $mobile_lg) {
                bottom: 0.5rem;
            }

            &-item {
                border: 0;
                padding: 0;
                width: 1rem;
                height: 1rem;
                margin: 1.5rem;

                @media(max-width: $tablet_md) {
                    margin: 1rem;
                }

                @media(max-width: $tablet) {
                    margin: 0.5rem;
                }

                @media(max-width: $mobile_lg) {
                    margin: 0.2rem;
                }

                background-color: $col_white;

                border-radius: 50%;
                z-index: 1000;

                &.active {
                    background-color: $col_green;
                }
            }
        }
        
        &__navigation {
            .slider-btn-prev,
            .slider-btn-next {
                position: absolute;

                top: 50%;
                transform: translateY(-50%);

            
                padding: 0;
                display: flex;
                align-items: center;
                justify-content: center;
                width: 3rem;
                height: 3rem;
                opacity: 1;

                border: 1px solid $col_green;
                border-radius: 18rem;

                background-color: $col_white;

                transition: opacity $transition-rules;
                z-index: 1000;

                &:hover,
                &:focus {
                    opacity: 0.8;
                }

                &:active {
                    opacity: 0.6;
                }
            }

            .slider-btn-prev {
                left: 2rem;

                @media(max-width: $mobile_lg) {
                    left: 1rem;
                }
            }

            .slider-btn-next {
                right: 2rem;
                transform: translateY(-50%) rotate(180deg);

                @media(max-width: $mobile_lg) {
                    right: 1rem;
                }
            }
        }
    }
</style>