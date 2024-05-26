<template>
    <section class="main-banner">
        <div class="leftside">
            <h1 class="leftside__title">Learn Language</h1>
            <div class="leftside__description">
                Мощный сервис, разработанный для образования на разных уровнях, который позволяет быстро и эффективно проверять код учеников на наличие ошибок, улучшать его качество и повышать производительность. <span>Learn Language</span> разработан учителями, для учителей, чтобы повысить уровень комфорта ваших занятий!
            </div>
            <div class="leftside-btn">Начать сейчас!</div>
        </div>
        <div class="rightside">
            <img src="@/assets/mainBanner.svg" alt="" class="rightside__banner">
        </div>
    </section>
</template>
<script setup>

</script>
<style scoped>
    .main-banner {
        flex: 1 0 auto;
        display: flex;
        justify-content: space-between;
        align-items: center;
        width: 100%;
        padding: 5% 50px;

        font-size: 20px;
        font-family: 'Open Sans';
        font-weight: 400;
    }

    .leftside {
        width: 45%;
        display: flex;
        flex-direction: column;
        gap: 50px;
    }
    
    .leftside__title {
        font-size: 40px;
        letter-spacing: 4px;
        position: relative;
    }

    .leftside__title::before {
        content: '';
        position: absolute;
        top: 120%;
        width: 20%;
        height: 5px;
        background: #473BF0;
    }

    .leftside__description {
        font-weight: 300;
    }

    .leftside__description span {
        font-weight: 600;
    }

    .leftside-btn {
        display: inline-block;
        text-align: center;
        width: 200px;
        height: 40px;
        border-radius: 10px;
        line-height: 40px;
        font-weight: 600;
        background: #81A4CD;
        transition: .5s
    }

    .leftside-btn:hover {
        background: #95b6dc;
        transform: scale(1.1);
        cursor: pointer;
    }
    
    .rightside {
        width: 45%;
        text-align: center
    }

    .rightside__banner {
        max-width: 80%;
    }
</style>

<!-- REWORK!!! -->