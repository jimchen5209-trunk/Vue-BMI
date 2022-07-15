<template>
    <div class="my-2">
        <label for="price" class="block text-sm font-medium text-gray-700">{{props.title}}</label>
        <div class="mt-1 relative rounded-md shadow-sm">
            <input type="number" name="price" id="price"
                class="focus:ring-emerald-500 focus:border-emerald-500 block w-full pl-4 pr-12 sm:text-sm border-gray-300 rounded-md"
                placeholder="0.00" :value="props.modelValue" @input="$emit('update:modelValue', $event.target.value)">
            <div class="absolute inset-y-0 right-4 pl-3 flex items-center pointer-events-none">
                <span class="text-gray-500 sm:text-sm"> {{props.footer}} </span>
            </div>
        </div>
    </div>
</template>

<script setup>
import { defineProps } from 'vue'

const props = defineProps({
    title: { type: String, required: true },
    footer: { type: String, required: true },
    modelValue: { type: Number}
})
</script>