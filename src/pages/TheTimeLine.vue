<script setup>
    import TimelineItem from '../components/TimelineItem.vue'
    import {validateTimelineItems, validateSelectOptions, validateActivities} from '../validators';

    defineProps({
        timelineItems: {
            requred: true,
            type: Array,
            validator: validateTimelineItems
        },
        activitySelectOptions: {
            required: true,
            type: Array,
            validator: validateSelectOptions
        },
        activities: {
            required: true,
            type: Array,
            validator: validateActivities
        }
    })
</script>

<template>
    <div class="mt-7">
        <ul>
            <TimelineItem v-for="timelineItem in timelineItems" :key="timelineItem.hour" :timeline-item="timelineItem" :activity-select-options="activitySelectOptions" :activities="activities" />
        </ul>
    </div>
</template>