<template>
  <main>
    <main-menu />
    <service-row />
    <contact-row />
  </main>
</template>

<script setup>
import MainMenu from './components/MainMenu.vue'
import ServiceRow from './components/ServiceRow.vue'
import ContactRow from './components/ContactRow.vue'
</script>

<style lang="scss">
body {
  background-color: #222;
}
</style>
