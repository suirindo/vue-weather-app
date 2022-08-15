<template>
  <Title />
  <Form @submit-form = "getWeather" />
  <Results :results="results" />


</template>


<script setup>
import { reactive } from "vue"
import axios from "axios"
import Title from "./components/Title.vue"
import Form from "./components/Form.vue"
import Results from "./components/Results.vue"


const results = reactive({
  country: "",
  cityName: "",
  temperature: "",
  conditionText: "",
  icon: ""
})


const getWeather = () => {
  axios.get("http://api.weatherapi.com/v1/current.json?key=730baec80e6c45fd91b85720212612&q=London&aqi=no")
  .then(res => {
    results.country = res.data.location.country,
    results.cityName = res.data.location.name,
    results.temperature = res.data.current.temp_c,
    results.conditionText = res.data.current.condition.text,
    results.icon = res.data.current.condition.icon
  }) // weatherAPIから送られてきたデータの受け取り処理を行う
}

</script>




