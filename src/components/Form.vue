<template>
    <form @submit.prevent="" class="form">
        <div class="form-group">
            <input type="text" :id="nameId" class="form-control" placeholder=" " autocomplete="off" required>
            <label :for="nameId" class="form-label">Ім'я</label>
        </div>
        <div class="form-group">
            <textarea :id="messageId" class="form-textarea" placeholder=" " autocomplete="off" required></textarea>
            <label :for="messageId" class="form-label">Повідомлення</label>
        </div>
        <v-btn x-large dark>OK</v-btn>
    </form>
</template>

<script>
    export default {
        props: ['nameId', 'messageId'],
    }
</script>

<style lang="scss">
    .form {
        display: flex;
        flex-direction: column;
        width: 100%;

        &__button {

            margin-left: auto;
        }
    }
</style>