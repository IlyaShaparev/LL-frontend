<template>
  <GuestLayout>
    <TeacherForm />
  <!-- <MainBanner /> -->
  </GuestLayout>
</template>

<script setup>
  import GuestLayout from './layouts/GuestLayout.vue';
  import TeacherForm from '@/components/TeacherForm.vue'

  // import MainBanner from '@/components/MainBanner.vue'

</script>

<style>
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
  html, body {
    background-color: aliceblue;
    height: 100%;
  }

  #app {
    display: flex;
    flex-direction: column;
    min-height: 100%;
  }
</style>
