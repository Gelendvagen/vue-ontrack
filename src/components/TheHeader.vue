<script setup>
    import TheLogo from './TheLogo.vue'
    import TheHeaderProgress from './TheHeaderProgress.vue'

    const emit = defineEmits(['goToTimeLine', 'goToProgress'])
</script>

<template>
<header class="sticky top-0 z-20 flex item-center justify-between border-b bg-white p-3">
    <TheLogo @click="emit('goToTimeLine')" />
    <TheHeaderProgress @click="emit('goToProgress')" />
  </header>
</template>