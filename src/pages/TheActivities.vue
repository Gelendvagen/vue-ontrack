<script setup>
    import {TrashIcon} from '@heroicons/vue/24/outline'
    import BaseButton from '../components/BaseButton.vue'
    import BaseSelect from '../components/BaseSelect.vue'

    const periodSelectOptions = [{
        value: 15,
        label: '0:15'
    }]
</script>

<template>
    <div>
        <ul class="divide-y">
            <ActivityItem v-for="activity in activities" :key="activity" :activity="activity" />
        </ul>
    </div>
</template>