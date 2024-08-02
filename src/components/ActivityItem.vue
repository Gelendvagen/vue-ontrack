<script setup>
    import {TrashIcon} from '@heroicons/vue/24/outline'
    import BaseButton from './BaseButton.vue'
    import BaseSelect from './BaseSelect.vue'
    import {ref} from 'vue'
    import {PERIOD_SELECT_OPTIONS} from '../constants'

    defineProps({
        activity: {
            required: true,
            type: String
        }
    })

    const secondsToComplete = ref(null)
</script>

<template>
    <li class="flex flex-col gap-2 p-4">
        <div class="flex items-center gap-2">
            <BaseButton>
                <TrashIcon class="h-8" />
            </BaseButton>
            <span class="truncate text-xl">{{activity}}</span>
        </div>
        <div>
            <BaseSelect class="font-mono" placeholder="h:mm" :options="PERIOD_SELECT_OPTIONS" :selected="secondsToComplete" @select="secondsToComplete = $event" />
        </div>
    </li>
</template>