<template>
  <div class="flex justify-center items-center h-screen w-screen">
    <div id="card" class="rounded-[10px] bg-white flex flex-col w-screen max-w-sm px-6 py-8">
      <h1 class="text-center text-emerald-500 my-4">BMI 計算器</h1>
      <InputGroup title="身高" footer="公分" v-model="height" />
      <InputGroup title="體重" footer="公斤" v-model="weight" />
      <BMIResult :result="result" />
      <hr class="my-4">
      <BMIHelp />
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from "vue"
import InputGroup from './components/InputGroup.vue'
import BMIResult from './components/BMIResult.vue'
import BMIHelp from './components/BMIHelp.vue'

const height = ref(168);
const weight = ref(76);
const result = computed(() => weight.value / Math.pow(height.value / 100, 2));

</script>