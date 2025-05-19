<script setup>
  import Header from './components/Header.vue';

</script>

<template>
  <Header />
  <main>
    <router-view v-slot="{ Component }">
      <transition name="page" mode="out-in">
        <component :is="Component" />
      </transition>
    </router-view>
  </main>
</template>

<style>

  :root {
    --hovered-color: #C029E1;
    --active-color: #40E4E8;
    --text-color: #c3bebe;
    --transition-speed: 0.3s;
    --title-font-size: 3em;
    --font-size: 1.5em;
    user-select: none;
  }

  .center {
    display: flex;
    flex-wrap: wrap;
    align-content: center;
  }

</style>

<style scoped>

  main {
    height: calc(100vh - 5rem);
    display: flex;
    flex-wrap: wrap;
    align-content: center;
  }

  .page-enter-active,
  .page-leave-active {
    transition: opacity 0.3s, transform 0.3s;
  }

  .page-enter-from {
    opacity: 0;
    transform: translateY(20px);
  }

  .page-leave-to {
    opacity: 0;
    transform: translateY(-20px);
  }

</style>
