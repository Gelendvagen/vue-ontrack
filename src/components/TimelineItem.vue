<script setup>
    import BaseSelect from './BaseSelect.vue'
    import {isActivityValid, isTimeLineItemValid, validateActivities, validateSelectOptions, isNull} from '../validators'
    import TimelineHour from './TimelineHour.vue'

    const props = defineProps({
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
        emit('selectActivity', props.activities.find((activity) => activity.id === id)) || null
    }

    const emit = defineEmits({
        selectActivity(activity) {
            return isNull(activity) || isActivityValid(activity)
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
            @select="selectActivity"
        />
    </li>
</template>