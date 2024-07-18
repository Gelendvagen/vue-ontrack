<script setup>
    import {XMarkIcon} from '@heroicons/vue/24/outline'
</script>

<template>
    <div class="flex gap-2">
            <button class="rounded bg-gray-100 p-3 enabled:hover:bg-gray-200 disabled:cursor-not-allowed disabled:opacity-50">
                <XMarkIcon class="h-8" />
            </button>
            <select name="" id="" class="w-full truncate rounded bg-gray-100 py-1 px-2 text-2xl">
                <option selected disabled value="">{{placeholder}}</option>
                <option v-for="{value, label} in options" :key="value" :value="value">
                    {{label}}
                </option>
                <option value="">Coding</option>
                <option value="">Reading</option>
                <option value="">Training</option>
            </select>
        </div>
</template>