<script setup lang="ts">
import { ref } from 'vue'

const data = ref('')

function setData(event) {
  console.log(event.target.value);

  const price = event.target.value.replace(/[^\d\.,]+/g, '')

  if(/,$/.test(price)) return

  console.log('price', price);

  const numberPrice = Number.parseFloat(price.replace(/,/, '.'))
  console.log('floatPrice', numberPrice);
  
  data.value = numberFormat(numberPrice).replace(/\s₽/, '')
  console.log('data.value', data.value);
}

function numberFormat(value: number, options = {}) {
  return new Intl.NumberFormat('ru-RU', {
    style: 'currency',
    currency: 'RUB',
    maximumFractionDigits: 2,
    ...options
  })
    .format(value)
    .replace(/([.,])00/g, '')

  // return new Intl.NumberFormat("ru-RU", options).format(value)
}
</script>

<template>
  <input v-model="data" class="custom-input" @input="setData" />
</template>

<style>
.custom-input {
  height: 40px;
}
</style>
