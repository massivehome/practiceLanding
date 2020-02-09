<template>
    <section id="preferences" class="preferences">
        <div class="preferences__cards">
            <div class="card col-xs-2 col-sm-6 col-md-2" v-for="(card, key) in cards" :key="key">
                <div class="card__content">
                    <div class="card__picture">
                        <v-icon large color="dark darken-2">mdi-{{ card.icon }}</v-icon>
                    </div>
                    <div class="card__title">
                        {{ card.name }}
                    </div>
                    <div class="card__description">
                        {{ card.message }}
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
                        icon: 'airplane',
                        name: 'First preference',
                        message: 'text text text',
                    },
                    card_2: {
                        icon: 'account-check-outline',
                        name: 'Second preference',
                        message: 'text',
                    },
                    card_3: {
                        icon: 'bell',
                        name: 'Third preference',
                        message: 'text',
                    },
                    card_4: {
                        icon: 'car-wash',
                        name: 'Fourth preference',
                        message: 'text',
                    }
                }
            };
        },
    }
</script>

<style lang="scss">
    .preferences {

        &__cards {
            display: flex;
            flex-direction: row;
            flex-wrap: wrap;
            justify-content: space-between;
        }
    }
</style>