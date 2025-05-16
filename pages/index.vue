<template>
    <UCard class="relative max-w-2xs">
        <template #header>
            <h1 class="text-2xl font-bold">Doca 1 - Motores</h1>
        </template>

        <div class="flex gap-3">
            <p>Vagas disponiveis</p>
            <UBadge color="neutral" >4</UBadge>
        </div>

        <div class="group absolute bottom-1 right-1 transition-all duration-300 flex align-middle items-center gap-2">  
        <p class="hidden text-xs group-hover:block">Caminhão na doca</p>
        <div class="bg-green-500 w-4 h-4 rounded-full   animate-pulse shadow-2xl shadow-emerald-300">
        </div>
        </div>
    </UCard>
</template>