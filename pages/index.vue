<script setup>
import { ref, onMounted } from 'vue'

const data = ref(null)
const error = ref(null)

async function fetchData() {
    try {
        console.log('Starting fetch request to http://localhost:5276/dock')
        const response = await fetch("http://localhost:5276/dock", {
            method: 'GET',
            headers: {
                'Accept': 'application/json',
                'Content-Type': 'application/json'
            },
            mode: 'cors'
        })

        console.log('Response status:', response.status)
        console.log('Response headers:', response.headers)

        if (!response.ok) {
            throw new Error(`HTTP error! status: ${response.status}`)
        }

        const jsonData = await response.json()
        console.log('Received data:', jsonData)
        data.value = jsonData
    } catch (error) {
        console.error('Detailed error:', {
            message: error.message,
            name: error.name,
            stack: error.stack
        })
        error.value = error.message
    }
}
const time = ref(new Date().toLocaleTimeString([], { hour: '2-digit', minute: '2-digit', second: '2-digit' }))
const updateTime = () => {
    time.value = new Date().toLocaleTimeString([], { hour: '2-digit', minute: '2-digit', second: '2-digit' })
}
onMounted(() => {
    setInterval(() => {
        updateTime()
    }, 1000)
})
onMounted(() => {
    console.log('Component mounted, initiating fetch')
    fetchData()
})
</script>

<template>
    <main class="flex flex-col w-full">
        <nav class="bg-[#346335] text-white justify-between flex items-center p-4 w-full">
            <h1 class="text-lg font-semibold">Dock App</h1>
            <p class="text-lg font-semibold">{{ time }}</p>
        </nav>
        <div class="flex flex-row max-w-full">
            <div class="flex flex-col max-w-full">
                <div class="my-3 mx-3 flex justify-between align-middle items-center">
                    <Search />
                    <Filters />
                </div>
                <div v-if="error" class="error">
                    Error: {{ error }}
                </div>
                <div v-else-if="!data">
                    Test
                </div>
                <div v-else>
                    <h2 class="text-3xl font-semibold px-4 py-2 text-neutral-950">On dock <span>{{ data.length }}</span>
                    </h2>
                    <div v-for="dock in data" :key="dock.id" class="flex flex-wrap gap-4 p-4">
                        <Dock :name=dock.name color="green" />
                    </div>
                </div>
            </div>
            <AddTruck />
        </div>
    </main>
</template>

<style scoped>
.error {
    color: red;
    padding: 10px;
}
</style>