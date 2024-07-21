<script setup>
    import {XMarkIcon} from '@heroicons/vue/24/outline'
</script>

<template>
    <button class="rounded bg-gray-100 p-3 enabled:hover:bg-gray-200 disabled:cursor-not-allowed disabled:opacity-50">
        <slot></slot>
     </button>
</template>