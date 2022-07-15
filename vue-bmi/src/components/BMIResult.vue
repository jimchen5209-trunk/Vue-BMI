<template>
    <div id="result" class="flex justify-center items-end my-6">
        <span class="text-xl">
            BMI
        </span>
        <span class="text-6xl">
            {{ props.result.toFixed(2) }}
        </span>
    </div>

    <div class="my-4 text-center rounded-[5px] py-4 text-xl" :class="weightText[1]">
        您的體重為「{{weightText[0]}}」
    </div>
</template>

<script setup>
import { defineProps, computed } from 'vue';

const props = defineProps({
    result: {type: Number, required: true}
})

const weightText = computed(() => {
    if (props.result < 18.5) {
        return ['過輕', 'bg-cyan-400']
    } else if (props.result < 24) {
        return ['正常', 'bg-green-400']
    } else if (props.result < 27) {
        return ['過重', 'bg-amber-400']
    } else if (props.result < 30) {
        return ['輕度肥胖', 'bg-orange-400']
    } else if (props.result < 35) {
        return ['中度肥胖', 'bg-red-400']
    } else {
        return ['重度肥胖', 'bg-red-500']
    }
})
</script>