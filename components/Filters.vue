<template>
    <div class="flex justify-between mx-3 space-x-2">
        <div class="hidden lg:flex lg:space-x-2 lg:max-w-lg lg:mr-4">
            <button class="bg-green-800 min-w-20 max-w-full h-10 rounded-lg text-white px-3">All</button>
            <button class="bg-gray-200 min-w-20  max-w-full h-10 rounded-lg text-gray-600 px-3">PowerTrain</button>
            <button class="bg-gray-200 min-w-20 max-w-full h-10 rounded-lg text-gray-600 px-3">Assembly</button>
            <button class="bg-gray-200 min-w-20 max-w-full h-10 rounded-lg text-gray-600 px-3">Body</button>
        </div>
        <div class="flex space-x-2 h-10 w-xs">
            <button
                class="bg-green-500 rounded-full text-transparent h-6 w-6 lg:text-white lg:px-3 md:rounded-md lg:w-full lg:h-10">On
                Time</button>
            <button
                class="bg-orange-400 rounded-full text-transparent h-6 w-6 lg:text-white lg:px-3 md:rounded-md lg:w-full lg:h-10">Late</button>
            <button
                class="bg-red-600 rounded-full text-transparent h-6 w-6 lg:text-white lg:px-3 md:rounded-md lg:w-full lg:h-10">Very
                Late</button>
        </div>
    </div>
</template>