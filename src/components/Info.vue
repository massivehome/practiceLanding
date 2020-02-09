<template>
    <section id="information" class="information">
        <div class="information__list row">
            <div class="information__card card col-sm-12 col-md-4" v-for="(card, key) in cards" :key="key">
                <div class="information__content card__content">
                    <picture class="card__picture information__picture">
                        <img :src="card.image" class="img-responsive">
                    </picture>
                    <div class="information__title card__title">
                        {{ card.title }}
                    </div>
                    <div class="information__description card__description">
                        {{ card.description }}
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
                cards: {
                    card_1: {
                        image: 'https://www.adventuresglobal.net/ag/wp-content/uploads/2019/04/Annapurna-Sanctuary-960x1149.png',
                        title: 'Annapurna',
                        description: 'The Annapurna Mountain Range (Annapurna Massif) is situated in the Himalayas in Nepal and consists of several peaks, with the tallest reaching a height of over 8,000 meters. The mountains and the regions surrounding them are protected by the Annapurna Conservation Area, which is the largest conservation area in Nepal.',
                    },
                    card_2: {
                        image: 'https://cdn.britannica.com/14/75514-120-05A119F2/K2-district-Karakoram-Range-portion-Gilgit-Baltistan-region.jpg',
                        title: 'K2',
                        description: 'Climbing K2 is much more challenging and far more dangerous than climbing Everest via the standard North or South side routes, and for this reason we plan to keep our team size small and comprised of qualified climbers, supported by some of the best climbing Sherpas and mountain guides in the world',
                    },
                    card_3: {
                        image: 'https://lh3.googleusercontent.com/proxy/bkAPXA_YOBY7kpJ83sNdlrGEQKzVnZxDdnpeTCnjK9OcEIVfxmCQCC-kveULZ70e1woT9VhB_8rRiQCjPIUT-PyQdI4-mtQ6l_IiWuRByIUq0XMiIhF_myr9ew',
                        title: 'Jomolungma',
                        description: 'The ascent of Mount Ever­est is an unpar­al­leled jour­ney of both leg­endary and epic pro­por­tion. Join us as we climb Mtount Ever­est to the top of the world to gain the mountaineer’s ulti­mate prize',
                    },
                },
            };
        },
    }
</script>

<style lang="scss" scoped>
    .information {
        position: relative;
        padding-top: 0px;
        background-color: transparent !important;

        &::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            border-bottom: 15px solid #757575;
            border-left: 5px solid #757575;
            border-right: 5px solid #757575;
            border-top: 0;
            background-color: #424242;
            opacity: .8;
            z-index: 1;
        }

        &__list {
            display: flex;
            flex-direction: row;
            flex-wrap: wrap;
        }

        &__content {
            padding: 30px 45px;

            &::before {
                display: none;
            }
        }

        &__picture {
            display: flex;
            max-height: 250px;
            margin-bottom: 20px;
        }

        &__title {
            color: #fff;
        }

        &__description {
            color: #fff;
        }
    }
</style>