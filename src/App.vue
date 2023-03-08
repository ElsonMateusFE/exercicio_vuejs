<script setup>
import { reactive } from 'vue';
import Formulario from './components/Formulario/Formulario.vue'
import Aritmetrica from './components/Formulario/Aritmetrica.vue';

const estado = reactive({
  filtro: '+',
  valorA: '',
  valorB: ''
})

const adicaoDosValores = () => {
  return Number(estado.valorA) + Number(estado.valorB)
}

const subtracaoDosValores = () => {
  return Number(estado.valorA) - Number(estado.valorB)
}

const multiplicacaoDosValores = () => {
  return Number(estado.valorA) * Number(estado.valorB)
}

const divisaoDosValores = () => {
  return Number(estado.valorA) / Number(estado.valorB)
}

const getOperatoresFiltros = () => {
  const { filtro } = estado

  switch (filtro) {
    case '÷':
      return divisaoDosValores()
    case '-':
      return subtracaoDosValores()
    case 'x':
      return multiplicacaoDosValores()
    default:
      return adicaoDosValores()
  }
}
</script>

<template>
  <div class="container mt-3">
    <h1 class="text-center">Calculadora Aritmétrica</h1>
    <Aritmetrica :estado-filtro="e => estado.filtro = e.target.value" />
    <Formulario :estado-a="e => estado.valorA = e.target.value" :estado-b="e => estado.valorB = e.target.value" :estado-filtro="estado.filtro" :operatores-filtros="getOperatoresFiltros()" />
  </div>
</template>

<style scoped></style>
