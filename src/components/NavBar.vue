<template>
    <nav class="navbar">
        <router-link to="/" class="navbar-item"><span>Home</span></router-link>
        <router-link to="/about" class="navbar-item"><span>About</span></router-link>
        <router-link to="/profile" class="navbar-item"><span>Profile</span></router-link>
        <router-link to="/dashboard" class="navbar-item"><span>Dashboard</span></router-link>
    </nav>
</template>
  
<script setup>
</script>
  
<style scoped>
    .navbar {
        width: 50%;
        display: flex;
        justify-content: space-around;
        align-items: center;
        gap: 20px;
    }

    .navbar-item {
        padding: 10px;
        font-family: 'Open Sans';
        font-weight: 600;
        font-size: 20px;
    }

    .navbar-item:hover span {
        cursor: pointer;
        border-bottom: 2px solid #473BF0;
    }
</style>