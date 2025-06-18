<template>
    <div class="w-[274px] h-[274px] px-4 pt-4 bg-white rounded-lg shadow-md flex flex-col relative hover:shadow-lg">
        <div class="flex justify-between items-center mb-4"> 
            <p class="font-light text-neutral-950">{{ name }} <bold>1/4</bold></p>
            <p>ICON</p>
        </div>
        <div class="flex flex-col mb-4">
            <p class="text-neutral-800">{{carrier}}</p>
            <p class="text-neutral-950 mb-3">{{invoiceNumber}}</p>
            <p class="text-neutral-800">{{type}}</p>
        </div>
        <div class="flex bottom-2 absolute">
            <div>
                <p class="font-light text-neutral-700">Dock Time</p>
                <p class="font-semibold text-neutral-950 text-2xl">{{initTime}}</p>
            </div>
            
        </div>
        <div class="absolute bottom-2 right-2 space-x-2">
                <span :class="colorClass"></span>
        </div>
    </div>
</template>

<script setup>
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
            default: 'waiting for invoice...'
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
        return `bg-${props.color}-600 block w-7 h-7 rounded-full`
    })
</script>