<template>
    <section id="feedback" class="feedback">
        <div class="feedback__form col-sm-12 col-md-5">
            <div class="feedback__title">
                Зв'язок з нами:
            </div>
            <Form :name-id="'name_1'" :message-id="'message_1'"></Form>
        </div>
    </section>
</template>

<script>
    import Form from './Form';

    export default {
        methods: {
            submit() {

            }
        },
        components: {
            Form,
        },
    }
</script>

<style lang="scss">
    .feedback {
        position: relative;
        display: flex;
        flex-direction: column;
        align-items: center;
        padding-bottom: 20px;

        &::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            border-top: 15px solid #757575;
            border-left: 5px solid #757575;
            border-right: 5px solid #757575;
            border-bottom: 1px solid #757575;
            background-color: #424242;
            opacity: .8;
            z-index: 1;
        }

        &__title {
            font-size: 22px;
            color: #fff;
            z-index: 1;
        }

        &__form {
            display: flex;
            flex-direction: column;
            justify-content: center;
            z-index: 2;
        }
    }
</style>