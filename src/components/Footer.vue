<template>
    <footer class="footer">
        <v-container>
            <ul class="footer__list">
                <li class="footer__item col-sm-12 col-md-4">
                    <ul class="footer-menu">
                        <li class="footer-menu__item" v-for="item in menu">
                            <a :href="item.href" class="footer-menu__link">
                                {{ item.name }}
                            </a>
                        </li>
                    </ul>
                </li>
                <li class="footer__item col-sm-12 col-md-5">
                    <div class="footer__form">
                        <Form :name-id="'name_2'" :message-id="'message_2'"></Form>
                    </div>
                </li>
                <li class="footer__item col-sm-12 col-md-3">
                    <ul class="footer-social">
                        <li class="footer-social__item">
                            <a href="" class="footer-social__link">
                                facebook
                            </a>
                        </li>
                        <li class="footer-social__item">
                            <a href="" class="footer-social__link">
                                instagram
                            </a>
                        </li>
                    </ul>
                </li>
            </ul>
        </v-container>
    </footer>
</template>

<script>
    import Form from './Form';

    export default {
        data() {
            return {
                menu: {
                    aboutUs: {
                        href: '#carousel',
                        name: 'Про нас',
                    },
                    preferences: {
                        href: '#preferences',
                        name: 'Переваги',
                    },
                    feedback: {
                        href: '#feedback',
                        name: "Зв'язок",
                    },
                    info: {
                        href: '#information',
                        name: 'Інформація',
                    },
                    squad: {
                        href: '#squad',
                        name: 'Наша команда',
                    },
                }
            };
        },
        components: {
            Form,
        },
    }
</script>

<style lang="scss">
    .footer {
        position: relative;
        padding: 30px;
        background-color: #424242;

        &__list {
            display: flex;
            flex-direction: row;
            flex-wrap: wrap;
            align-items: stretch;
            justify-content: space-between;
            z-index: 2;
        }
    }

    .footer-menu {
        display: flex;
        flex-wrap: wrap;
        flex-direction: column;

        &__link {
            display: flex;
            padding: 5px 0;
            font-size: 14px;
            font-weight: 600;
            color: #fff;
            text-transform: uppercase;
            text-decoration: none;
        }
    }

    .footer-social {
        display: flex;
        flex-direction: row;
        align-items: flex-end;
        justify-content: flex-end;
        height: 100%;

        &__item {

            &:not(:last-child) {
                margin-right: 10px;
            }
        }

        &__link {
            display: flex;
            padding: 0 5px;
            font-size: 15px;
            font-weight: 600;
            color: #fff;
            text-transform: uppercase;
            text-decoration: none;
        }
    }

    @media screen and (max-width: 960px) {
        .footer {
            padding: 0;
        }
    }
</style>