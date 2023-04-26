<script setup lang="ts">

const props = defineProps()
const id  = Math.random()
</script>

<template>
    <div class="flex gap-2 px-2 py-2">
        <div class="flex-none grid place-content-center">
            <div class="rounded-full bg-gray-300 overflow-hidden">
                <img class="h-12" :src="`https://api.dicebear.com/6.x/open-peeps/svg?seed=${id}`"/>
            </div>
        </div>
        <div class="flex flex-col flex-1">
            <div class="text-lg font-semibold">Contact</div>
            <div class="text-sm text-gray">123</div>
        </div>
    </div>
</template>