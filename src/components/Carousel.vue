<template>
    <div id="carousel" class="carousel">
        <v-carousel :cycle="false"
                    hide-delimiter-background
                    delimiter-icon="mdi-minus">
            <v-carousel-item v-for="(slide, i) in slides" :key="i">
                <v-sheet height="100%" tile>
                    <v-row class="carousel__item fill-height"
                           align="center"
                           justify="center">
                        <picture class="carousel__picture" v-if="slide.image">
                            <img :src="slide.image" alt="">
                        </picture>
                        <div class="carousel__text">
                            {{ slide.text }}
                        </div>
                    </v-row>
                </v-sheet>
            </v-carousel-item>
        </v-carousel>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                slides: [
                    {
                        text: 'first slide',
                    },
                    {
                        image: 'https://exclusivesmedia.webjet.com.au/uploads/2018/02/Annapurna-Trek-8-min.jpg',
                    },
                    {
                        text: 'third slide',
                    },
                    {
                        text: 'fourth slide',
                    },
                ],
            };
        },
    }
</script>

<style lang="scss">
    .v-carousel {
        height: auto !important;
        background-color: #fff;
    }

    .carousel {

        &__item {
            display: flex;
            flex-direction: column;
        }
    }
</style>