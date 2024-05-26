<template>
    <HeaderComponent />
    <slot></slot>
    <FooterComponent />
</template>
<script setup>
    import HeaderComponent from '@/components/HeaderComponent.vue';
    import FooterComponent from '@/components/FooterComponent.vue'
</script>
<style lang="">
    
</style>