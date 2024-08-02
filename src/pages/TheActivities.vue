<script setup>
    import ActivityItem from '../components/ActivityItem.vue'

    defineProps({
        activities: {
            required: true,
            type: Array,
            //validator:
        }
    })
</script>

<template>
    <div>
        <ul class="divide-y">
            <ActivityItem v-for="activity in activities" :key="activity" :activity="activity" />
        </ul>
    </div>
</template>