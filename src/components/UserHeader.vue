<template>
    <div class="user__wrapper" @click="isShow = !isShow">
        <div class="info__wrapper">
            <img v-if="!isAuth" src="@/assets/user_inactive.png" alt="" class="user-icon">
            <img v-else src="@/assets/user_active.png" alt="" class="user-icon">
            <p>User Info</p>        <!-- Сделать зависимым от isAuth -->
        </div>
        <div v-if="isShow" class="login__wrapper">
            <!-- Переписать под авторизацию!!! -->
            <button v-if="!isAuth" class="btn reg-btn" @click="isAuth = true">Регистрация</button> 
            <button v-if="!isAuth" class="btn auth-btn" @click="isAuth = true">Авторизация</button>
            <button v-if="isAuth" class="btn auth-btn">Мой профиль</button>
            <button v-if="isAuth" class="btn logout-btn" @click="isAuth = false">Выйти</button>
        </div>
    </div>
</template>

<script setup>
    import {ref} from 'vue';

    let isAuth = ref(false);
    let isShow = ref(false);
</script>

<style scoped>
    .user__wrapper {
        width: 10%;
        position: relative;
        font-family: 'Open Sans';
        font-weight: 500;
        font-size: 16px;
        display: flex;
        justify-content: center;
    }

    .info__wrapper {
        display: flex;
        flex-flow: column nowrap;
        justify-content: center;
        align-items: center;
        flex-wrap: wrap;
    }

    .user-icon {
        width: 32px;
        height: auto;
    }

    .login__wrapper {
        display: flex;
        flex-flow: column;
        justify-content: center;
        align-items: center;
        gap: 10px;
        background-color: rgb(248,249,250);
        border: 1px solid #212121;
        border-radius: 20px;
        padding: 20px;
        position: absolute;
        top: 120%;
    }

    .btn {
        color: #212121;
        background-color: transparent;
        border: 1px solid #212121;
        border-radius: 5px;
        font-family: 'Open Sans';
        font-weight: 600;
        font-size: 16px;
        padding: 10px;
    }

    .login__wrapper:after {
        content: '';
        width: 0;
        height: 0;
        border: 15px solid transparent;
        border-bottom: 15px solid rgb(248,249,250);
        position: absolute;
        bottom: 100%;
    }
    .login__wrapper:before {
        content: '';
        width: 0;
        height: 0;
        border: 16px solid transparent;
        border-bottom: 16px solid #212121;
        position: absolute;
        bottom: 100%;
    }


    /*  */
</style>