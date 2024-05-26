<template >
    <header class="header">
        <LogoHeader />
        <NavBar />
        <UserHeader />
    </header>
</template>

<script setup>
    import NavBar from "@/components/NavBar.vue"
    import UserHeader from "@/components/UserHeader.vue"
    import LogoHeader from "@/components/LogoHeader.vue"
</script>

<style scoped>
    .header {
        width: 100%;
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 20px 50px;
        background-color: transparent;
    }
</style>