<script setup>
    import BaseSelect from './BaseSelect.vue'
    import {isActivityValid, isTimeLineItemValid, validateActivities, validateSelectOptions} from '../validators'
    import TimelineHour from './TimelineHour.vue'
    import {BUTTON_TYPE_DANGER, BUTTON_TYPE_WARNING, BUTTON_TYPE_SUCCESS, NULLABLE_ACTIVITY} from '../constants'
    import {ArrowPathIcon, PauseIcon, PlayIcon} from '@heroicons/vue/24/outline'
    import BaseButton from './BaseButton.vue'

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
        emit('selectActivity', findActivityById(id))
    }

    function findActivityById(id) {
        return props.activities.find((activity) => activity.id === id) || NULLABLE_ACTIVITY
    }

    const emit = defineEmits({
        selectActivity: isActivityValid
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
        <div class="flex w-full gap-2">
            <BaseButton :type="BUTTON_TYPE_DANGER">
                <ArrowPathIcon class="h-8" />
            </BaseButton>
            <div class="flex flex-grow items-center rounded bg-gray-100 px-2 font-mono text-3xl">
                00:00:00
            </div>
            <BaseButton :type="BUTTON_TYPE_WARNING">
                <PauseIcon class="h-8" />
            </BaseButton>
            <BaseButton :type="BUTTON_TYPE_SUCCESS">
                <PlayIcon class="h-8" />
            </BaseButton>
        </div>
    </li>
</template>