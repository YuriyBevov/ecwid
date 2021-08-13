<template>
    <section class="intro">
        <div class="cmn__wrapper">
            <div class="intro__wrapper">
                <div class="intro__content">
                    <h2 class="cmn__title">{{pageTitle}}</h2> 
                    <p class="cmn__text">{{pageDesc}}</p>
                    <a href="#" class="cmn__text cmn__text--thin cmn__text--green intro__link">{{pageLink}}</a>
                </div>

                <div class="intro__video">
                    <button aria-label="воспроизвести">
                        <img src="~@/assets/images/play-btn.png" alt="кнопка воспроизведения" width="60" height="60">
                    </button>
                </div>
            </div>
        </div>    
    </section>
</template>

<script>
    export default {
        data() {
            return {
                pageTitle: 'ДОБРО ПОЖАЛОВАТЬ В НАШ НОВЫЙ МАГАЗИН!',
                pageDesc : 'Мы садимся вязать, и вселенная вокруг начинает жить по-другому. Точнее, мы создаем собственную вселенную, в которой мы отдыхаем, вдохновляемся и создаем шедевры.                         Наш магазин за то, чтобы вы занимались своим любимым делом с удовольствием. Наш магазин – это место, где вам предложат пряжу и инструмент исключительного качества для создания лучших творений, которые вы только задумали. Наш магазин – это место, куда вы просто можете прийти поболтать и выпить чашечку кофе за вязанием',
                pageLink: 'Узнать о нас больше'
            }
        }
    }
</script>

<style lang="scss">
    @import '@/assets/styles/variables.scss';
    .intro {
        padding: 3.5rem 0;
        
        @media(max-width: $tablet_lg) {
            padding: 1.5rem 0;
        }

        &__wrapper {
            display: flex;
            flex-wrap: wrap;
            padding: 0 7rem;
            padding-right: 6.4rem;

            @media(max-width: $desktop) {
                padding: 0 3rem;
            }

            @media(max-width: $tablet) {
                position: relative;
                padding-bottom: 3rem;
            }
            
            @media(max-width: $mobile_lg) {
                padding: 1rem;
                padding-bottom: 3rem;
            }
        }

        &__content {
            width: 100%;
            max-width: 56.8rem;
            display: flex;
            flex-direction: column;
            align-items: flex-start;
            margin-right: auto;
            padding-right: 3rem;

            @media(max-width: $tablet_lg) {
                max-width: 70%;
            }

            @media(max-width: $tablet) {
                max-width: 100%;
            }

            @media(max-width: $mobile_lg) {
                padding-right: 0;
            }

            h2 {
                margin-bottom: 1.5rem;
            }

            p {
                text-align: left;
                line-height: 2.4rem;
                margin-bottom: 2rem;
            }

        }
        
        &__link {
            margin-top: auto;
            align-self: flex-end;
            text-decoration-line: underline;

            @media(max-width: $tablet_lg) {
                align-self: flex-start;
            }

            @media(max-width: $tablet) {
                position: absolute;
                bottom: 0;
                left: 3rem;
            }

            @media(max-width: $mobile_lg) {
                left: 1rem;
            }
        }

        &__video {
            position: relative;
            flex-grow: 1;
            max-width: 35rem;
            height: 21.3rem;
            align-self: center;

            border: 1px solid $col_green;
            background-color: $col_lightpink;

            

            @media(max-width: $tablet) {
                width: 100%;
            }

            button {
                
                position: absolute;
                top: 50%;
                left: 50%;

                width: 6rem;
                height: 6rem;
                transform: translate(-50%, -50%);
                opacity: 1;

                padding: 0;
                border: 0;
                background-color: transparent;

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