<template lang="">
    <div class="logo__wrapper">
        <div class="img__block">
            <img src="@/assets/webDev.png" alt="logo" class="logo-img">
        </div>
        <div class="brand__block">
            <h2 class="brand">
                <span>LearnLanguage</span>
            </h2>
        </div>
    </div>
</template>
<script setup>
</script>
<style scoped> 
    .logo__wrapper {
        min-width: 400px;
        max-width: 400px;
        border-radius: 20px;
        display: flex;
        justify-content: center;
        align-items: center;
        background-color: #473BF0;
    }

    .logo__wrapper:hover {
        cursor: pointer;
    }

    .img__block {
        width: 20%;
        display: flex;
        justify-content: center;
    }

    .logo-img {
        max-width: 100%;
        height: auto;
        padding: 20px;
    }

    .brand__block {
        width: 80%;
        align-self: stretch;
        border: 5px solid #473BF0;
        border-radius: 20px;
        font-family: 'Open Sans';
        font-weight: 600;
        background-color: aliceblue;
    }

    .brand {
        height: 100%;
        display: flex;
        align-items: center;
        justify-content: center;
    }

    .brand span {
        letter-spacing: 3px;
    }
</style>