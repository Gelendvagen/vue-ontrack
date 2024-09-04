<script setup>
  import TheHeader from './components/TheHeader.vue'
  import TheNav from './components/TheNav.vue'
  import {routes} from './router'
  import {currentPage} from './router'
</script>

<template>
  <TheHeader />
  <main class="flex flex-grow flex-col">
    <KeepAlive>
      <component :is="routes[currentPage]" />
    </KeepAlive>
  </main>
  <TheNav />
</template>