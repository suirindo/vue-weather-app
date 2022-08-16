<template>
    <div class = "results-country" v-if="country">{{ country }}</div>
    <div class = "results-city" v-if="cityName">{{ cityName }}</div>
    <div class = "results-temp" v-if="temperature">{{ temperature }}</div>
    <div class = "results-condition"  v-if="icon">
        <img :src="results.icon" alt="icon">
        <span>{{ results.conditionText }}</span>
    </div>
</template>

<script setup>
import { toRefs } from "vue"

    const props = defineProps({ // props :上位コンポーネントから渡されたデータのこと
        results: Object 
    })

const { country, cityName, temperature, icon, conditionText } = toRefs(props.results)
</script>