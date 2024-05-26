<template>
    <footer>
        <p class="copyright">
            © Copyright 2024 LearnLanguage.ru
        </p>
        <div class="social__wrapper">
            <ul class="social__list">
                <li class="social__list-item"><img :src="twitter" alt="" class="icon twitter"></li>
                <li class="social__list-item"><img :src="facebook" alt="" class="icon facebook"></li>
                <li class="social__list-item"><img :src="pinterest" alt="" class="icon pinterest"></li>
                <li class="social__list-item"><img :src="google" alt="" class="icon google"></li>
            </ul>
        </div>
    </footer>
</template>

<script>
    import twitter from '@/assets/Twitter.svg'
    import facebook from '@/assets/Facebook.svg'
    import pinterest from '@/assets/Pinterest.svg'
    import google from '@/assets/Google+.svg'

    export default {
        data() {
            return {
                twitter,
                facebook,
                pinterest,
                google
            }
        },
        name: 'FooterComponent'
    }
</script>

<style scoped>
    footer {
        flex: 0 0 auto;
        padding: 20px;
        display: flex;
        justify-content: center;
        align-items: center;
    }
    
    .copyright {
        position: absolute;
        left: 10%;
        font-size: 18px;
        font-weight: 600;
        font-family: 'Open Sans';
    }

    .social__list {
        display: flex;
        gap: 10px;
    }

    .social__list-item {
        width: 40px;
        height: 40px;
        border-radius: 50%;
        background: #333;
        display: flex;
        align-items: center;
        justify-content: center;
    }
</style>


<!-- © Copyright 2014 FreebiesXpress.com -->