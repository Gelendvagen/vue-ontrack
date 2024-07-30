<script setup>
    import {TrashIcon} from '@heroicons/vue/24/outline'
    import BaseButton from '../components/BaseButton.vue'
    import BaseSelect from '../components/BaseSelect.vue'
</script>

<template>
    <div>
        <ul>
            <li>
                <div>
                    <BaseButton>
                        <TrashIcon class="h-8" />
                    </BaseButton>
                    <span>Reading</span>
                </div>
                <div>
                    <BaseSelect />
                </div>
            </li>
        </ul>
    </div>
</template>