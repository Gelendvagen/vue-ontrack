<script setup>
    import TimelineItem from '../components/TimelineItem.vue'
    import {isTimeLineItemValid} from '../validators';

    defineProps({
        timelineItems: {
            requred: true,
            type: Array,
            validator: validateTimelineItems
        }
    })
</script>

<template>
    <div class="mt-7">
        <ul>
            <TimelineItem v-for="timelineItem in timelineItems" :key="timelineItem.hour" :timeline-item="timelineItem" />
        </ul>
    </div>
</template>