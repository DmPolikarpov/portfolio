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

<style scoped>

  main {
    padding: 2rem;
    min-height: calc(100vh - 8rem);


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
