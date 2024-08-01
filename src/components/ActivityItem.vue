<template>
    <li class="flex flex-col gap-2 p-4">
        <div class="flex items-center gap-2">
            <BaseButton>
                <TrashIcon class="h-8" />
            </BaseButton>
            <span class="truncate text-xl">{{activity}}</span>
        </div>
        <div>
            <BaseSelect class="font-mono" placeholder="h:mm" :options="periodSelectOptions" />
        </div>
    </li>
</template>