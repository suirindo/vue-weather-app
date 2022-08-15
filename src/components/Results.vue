<template>
    <div v-if="results.country">{{ results.country }}</div>
    <div v-if="results.cityName">{{ results.cityName }}</div>
    <div v-if="results.temperature">{{ results.temperature }}</div>
    <div v-if="results.icon">
        <img :src="results.icon" alt="icon">
        <span>{{ results.conditionText }}</span>
    </div>

</template>

<script setup>
    const props = defineProps({ // props :上位コンポーネントから渡されたデータのこと
        results: Object 
    })

</script>


