<template>
    <v-app class="justify-center" dark>
        <Header :menu="menu" :aside="aside" @update="updateAside"></Header>
        <v-navigation-drawer v-model="aside" app clipped>
            <ul class="menu menu--column">
                <li class="menu__item"
                    v-for="(item, key) in menu"
                    :key="key">
                    <a :href="item.link"
                       class="menu__link">
                        <v-icon>mdi-{{ item.icon }}</v-icon>
                        {{ item.title }}
                    </a>
                </li>
            </ul>
        </v-navigation-drawer>
        <v-content class="main">
            <v-container>
                <Carousel></Carousel>
                <Preferences></Preferences>
                <FeedbackComponent></FeedbackComponent>
                <Info></Info>
                <Squad></Squad>
            </v-container>
        </v-content>
        <Footer></Footer>
    </v-app>
</template>

<script>
    import Header from './components/Header.vue';
    import Carousel from './components/Carousel';
    import Preferences from './components/Preferences';
    import FeedbackComponent from './components/Feedback';
    import Info from './components/Info';
    import Squad from './components/Squad';
    import Footer from './components/Footer';

    export default {
        name: 'app',
        data() {
            return {
                aside: false,
                menu: {
                    aboutUs: {
                        link: '#carousel',
                        icon: 'home',
                        title: 'Про нас',
                    },
                    preferences: {
                        link: '#preferences',
                        icon: 'emoticon-happy',
                        title: 'Переваги',
                    },
                    feedback: {
                        link: '#feedback',
                        icon: 'nfc-variant',
                        title: "Зв'язок",
                    },
                    info: {
                        link: '#information',
                        icon: 'information',
                        title: 'Інформація',
                    },
                    squad: {
                        link: '#squad',
                        icon: 'account-group-outline',
                        title: 'Наша команда',
                    },
                },
            };
        },
        methods: {
            updateAside(data) {
                console.log(data);
                this.aside = data;
            },
        },
        components: {
            Header,
            Carousel,
            Preferences,
            FeedbackComponent,
            Info,
            Squad,
            Footer,
        },
    }
</script>

<style lang="scss">
    * {
        box-sizing: border-box;
    }

    html {
        scroll-behavior: smooth;
    }

    .v-application ul {
        list-style-type: none;
        padding: 0 !important;
        margin: 0 !important;
    }

    .v-application a {
        color: #fff !important;
        transition: .2s;

        &:hover {
            color: #c2c2c2 !important;
        }
    }

    .v-navigation-drawer__content {
        padding-top: 60px;
    }

    img {
        display: block;
        max-width: 100%;
        max-height: 100%;
        width: 100%;
        height: auto;
    }

    .form-group {
        position: relative;
        margin-bottom: 10px;
        padding-top: 20px;
    }

    .form-control,
    .form-textarea {
        width: 100%;
        padding: 10px 15px 7.5px;
        font-size: 14px;
        outline: none;
        color: #fff;
        background-color: transparent;
        border: 2px solid #757575;
        border-radius: 2px;
    }

    .form-textarea {
        height: auto;
        min-height: 70px;
    }

    .form-control:placeholder-shown + .form-label,
    .form-textarea:placeholder-shown + .form-label {
        font-size: 14px;
        transform: translateY(27px) translateX(15px);
    }

    .form-label {
        position: absolute;
        top: 0;
        left: 0;
        font-size: 12px;
        color: #fff;
        transform: translateY(0) translateX(0);
        transition: .2s;
    }

    section {
        padding: 40px 0;
    }

    button.btn-default {
        display: flex;
        justify-content: center;
        min-width: 150px;
        width: 100%;
        padding: 15px 30px 12.5px;
        font-size: 14px;
        text-align: center;
        color: #fff;
        text-transform: uppercase;
        line-height: 1;
        background-color: rgba(255, 255, 255, .4);
        border: 1px solid #424242;
        outline: none;
        transition: .2s;

        &:hover {
            background-color: #757575;
        }
    }

    #app {
        font-family: 'Roboto', sans-serif;
        color: #424242;
        overflow: hidden;
    }

    .container {
        padding: 0 12px !important;
    }

    .main {
        position: relative;
        padding-top: 60px;

        &::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-image: url('assets/main_background.png');
            background-repeat: no-repeat;
            background-attachment: fixed;
            background-position: center;
            background-size: cover;
            filter: brightness(.7);
        }
    }

    .menu {
        display: flex;
        flex-direction: row;

        &--column {
            flex-direction: column;
        }

        &__item {
            list-style-type: none;
        }

        &__link {
            display: flex;
            align-items: center;
            padding: 5px 10px;
            font-size: 14px;
            font-weight: 500;
            color: #fff;
            text-decoration: none;
            text-transform: uppercase;

            .v-icon {
                margin-right: 10px;
                color: #fff;
            }

            &--active {
                color: red !important;
            }

            &:hover {
                color: #eee;
            }
        }
    }

    .card {
        position: relative;
        padding: 0 15px;

        &__content {
            position: relative;
            padding: 20px;
            min-height: 200px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            text-align: center;
            line-height: 1;

            &::before {
                content: '';
                position: absolute;
                top: 0;
                left: 0;
                right: 0;
                bottom: 0;
                border-top: 5px solid #424242;
                background-color: #e6e8e6;
                opacity: .7;
                transition: .2s linear;
                z-index: 1;
            }

            &:hover {

                &::before {
                    top: -5px;
                    left: -5px;
                    right: -5px;
                    bottom: -5px;
                    border-width: 7.5px;
                }
            }
        }

        &__picture {
            display: flex;
            justify-content: center;
            margin-bottom: 20px;
            z-index: 1;

            img {
                object-fit: contain;
            }
        }

        &__title {
            font-size: 16px;
            font-weight: 600;
            margin-bottom: 10px;
            z-index: 1;
        }

        &__description {
            text-align: center;
            font-size: 14px;
            color: #757575;
            z-index: 1;
        }
    }
</style>
