<script setup>
import {ref, shallowRef, computed, watch, nextTick } from 'vue'
// import Chart from 'chart.js/auto'

const weights = ref ([])

const weightChartE1 = ref(null)

const weightChart = shallowRef(null)

const weightInput = ref(60.0)

const CurrentWeight = computed(() =>{
//Elements organized
  return weights.value.sort((a,b) => b.date - a.date)[0] || {weight:0}
})

const addweight = () => {
  weights.value.push({
    weight: weightInput.value,
    date: new Date().getTime()
  })
}

</script>

<template>
  <main>

<h1>Weight Tracker</h1>

<div class="current">
  <span>{{ CurrentWeight.weight}}</span>
  <small>Current weight (Kg)</small>
</div>

  </main>
</template>

<style>

</style>
