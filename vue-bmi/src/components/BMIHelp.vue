<template>
    <table>
        <tr v-for="(data, index) in datas" :key="index">
            <td class="text-lg px-2" :class="data[2]">{{data[1]}}</td>
            <td class="text-lg px-x" :class="data[2]">{{data[0]}}</td>
        </tr>
    </table>
</template>

<script setup>
import { reactive } from 'vue'

const datas = reactive([
    ['BMI ＜ 18.5', '過輕', 'text-cyan-400'],
    ['18.5 ≦ BMI ＜ 24', '正常', 'text-green-400'],
    ['24 ≦ BMI ＜ 27', '過重', 'text-amber-400'],
    ['27 ≦ BMI ＜ 30', '輕度肥胖', 'text-orange-400'],
    ['30 ≦ BMI ＜ 35', '中度肥胖', 'text-red-400'],
    ['BMI ≧ 35', '重度肥胖', 'text-red-500']]
);
</script>