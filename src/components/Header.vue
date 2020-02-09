<template>
    <v-app-bar fixed dark hide-on-scroll clipped-left>
        <v-container class="header__container">
            <div class="header__content">
                <div class="header__logo">
                    <img src="../assets/logo.png" alt="logo">
                </div>
                <v-spacer></v-spacer>
                <div class="header__menu">
                    <ul class="menu hidden-sm-and-down">
                        <li class="menu__item"
                            v-for="(item, key) in menu"
                            :key="key">
                            <a :href="item.link"
                               class="menu__link">
                                {{ item.title }}
                            </a>
                        </li>
                    </ul>
                </div>
                <div class="header__toggle hidden-md-and-top d-xs-flex d-sm-flex d-md-none d-lg-none d-xl-none">
                    <v-app-bar-nav-icon @click.stop="$emit('update', checkAside = !aside)" />
                </div>
            </div>
        </v-container>
    </v-app-bar>
</template>

<script>
    export default {
        props: ['menu', 'aside'],
        data() {
            return {
                checkAside: this.aside,
            };
        },
        created () {
            this.$vuetify.theme.dark = true
        },
        computed: {

        },
        methods: {
            active(link) {
                return location.hash === link;
            },
        },
    }
</script>

<style lang="scss" scoped>
    .header {
        background-color: #1E1E1E;

        &__content {
            position: relative;
            display: flex;
            flex-direction: row;
            align-items: center;
            padding: 15px 0;
        }

        &__logo {
            position: absolute;
            top: 10px;
            left: 0;
            display: flex;
            width: 65px;
            height: 80px;
        }

        &__menu {
            display: flex;
            align-items: center;
            margin-left: 80px;
        }
    }
</style>