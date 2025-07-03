<template>
    <div class="w-[300px] h-[300px] px-4 pt-4 bg-white rounded-2xl shadow-md flex flex-col relative hover:shadow-lg">
        <div class="flex justify-between items-center mb-2">
            <p class="font-medium text-neutral-950">{{ name }} <bold>1/4</bold>
            </p>
            <UIcon mode="svg" name="i-lucide-chevron-right" class="text-neutral-950 w-8 h-8 flex-shrink-0" />
        </div>
        <div class="flex flex-col mb-4 space-y-0.5">
            <p class="text-sm text-black">Carrier</p>
            <p class="text-neutral-800">{{ carrier }}</p>
            <p class="text-sm text-black">NF</p>
            <p class="text-neutral-800">{{ invoiceNumber }}</p>
            <p class="text-sm text-black">Type</p>
            <p class="text-neutral-800">{{ type }}</p>
        </div>
        <div class="flex bottom-2 absolute">
            <div>
                <p class="font-light text-neutral-700">Dock Time</p>
                <p class="font-bold text-neutral-950 text-2xl">{{ initTime }}</p>
            </div>

        </div>
        <div class="absolute bottom-2 right-2 space-x-2">
            <span :class="colorClass"></span>
        </div>
    </div>
</template>

<script setup>
import { UIcon } from '#components';

const props = defineProps({
    name: {
        type: String,
        default: 'Dock'
    },
    carrier: {
        type: String,
        default: 'Carrier Name'
    },
    invoiceNumber: {
        type: String,
        default: 'Waiting for invoice...'
    },
    type: {
        type: String,
        default: 'Unload/Load'
    },
    initTime: {
        type: String,
        default: '00:00'
    },
    color: {
        type: String,
        default: 'gray'
    }
})

const colorClass = computed(() => {
    return `bg-${props.color}-600 block w-8 h-8 rounded-full animate-pulse`
})
</script>