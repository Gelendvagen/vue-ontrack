<script setup>
    import BaseSelect from './BaseSelect.vue'
    import {isTimeLineItemValid} from '../validators.js'
    import {updateTimelineItem} from '../timeline-items'
    import {activitySelectOptions} from '../activities'
    import TimelineHour from './TimelineHour.vue'
    import TimelineStopwatch from './TimelineStopwatch.vue'

    defineProps({
        timelineItem: {
            requred: true,
            type: Object,
            validator: isTimeLineItemValid
        }
    })
</script>

<template>
    <li class="relative flex flex-col gap-2 border-t border-gray-200 py-10 px-4">
        <TimelineHour :hour="timelineItem.hour" />
        <BaseSelect 
            :selected="timelineItem.activityId" 
            :options="activitySelectOptions" 
            placeholder="Rest" 
            @select="updateTimelineItem(timelineItem, {activityId: $event})"
        />
        <TimelineStopwatch :timeline-item="timelineItem" />
    </li>
</template>