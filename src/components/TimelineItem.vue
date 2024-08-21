<script setup>
    import BaseSelect from './BaseSelect.vue'
    import {isActivityValid, isTimeLineItemValid, validateActivities, validateSelectOptions} from '../validators'
    import TimelineHour from './TimelineHour.vue'

    defineProps({
        timelineItem: {
            requred: true,
            type: Object,
            validator: isTimeLineItemValid
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

    function selectActivity(id) {
        emit('selectActivity', activities.find((activity) => activity.id === id))
    }

    const emit = defineEmits({
        selectActivity: isActivityValid
    })
</script>

<template>
    <li class="relative flex flex-col gap-2 border-t border-gray-200 py-10 px-4">
        <TimelineHour :hour="timelineItem.hour" />
        <BaseSelect :selected="timelineItem.activityId" :options="activitySelectOptions" placeholder="Rest" @select="selectActivity" />
    </li>
</template>