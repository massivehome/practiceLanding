<template>
    <section id="squad" class="squad">
        <div class="squad__list row">
            <div class="squad__card card col-sm-6 col-md-3" v-for="(member, key) in squad" :key="key">
                <div class="squad__content card__content">
                    <picture class="card__picture squad__picture">
                        <img :src="member.image" class="img-responsive">
                    </picture>
                    <div class="card__title">
                        {{ member.name }}
                    </div>
                    <div class="card__description">
                        {{ member.description }}
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
                squad: {
                    member_1: {
                        image: 'https://i.pinimg.com/originals/a7/4f/6c/a74f6ca956f238f1d08613de31a8564c.jpg',
                        name: 'Reinhold Messner',
                        description: 'He made the first solo ascent of Mount Everest, the first ascent of Everest without supplemental oxygen, along with Peter Habeler, and was the first climber to ascend all fourteen peaks over 8,000 metres (26,000 ft) above sea level.',
                    },
                    member_2: {
                        image: 'https://4sport.ua/stuff/mn1001/2011-11/8712/2.jpg',
                        name: 'Jerzy Kukuczka',
                        description: 'On 18 September 1987, he became the second man (after Reinhold Messner), to climb all fourteen eight-thousanders in the world; a feat which took him less than 8 years to accomplish.',
                    },
                    member_3: {
                        image: 'https://ichef.bbci.co.uk/news/ws/410/amz/worldservice/live/assets/images/2011/04/29/110429120943_loretan_304x304_ap.jpg',
                        name: 'Erhard Loretan',
                        description: ' was a Swiss mountain climber, often described as one of the greatest mountaineers of all times',
                    },
                },
            };
        },
    }
</script>

<style lang="scss">
    .squad {

        &__list {
            display: flex;
            flex-direction: row;
            flex-wrap: wrap;
            justify-content: space-around;
            /*margin: 0 -15px;*/
        }

        &__content {
            border-radius: 10px;

            &::before {
                border-radius: 10px;
            }
        }

        &__picture {
            display: flex;
            width: 100px;
            height: 100px;
            margin-bottom: 20px;

            img {
                border-radius: 50%;
                object-fit: cover !important;
            }
        }
    }
</style>