<script setup>
import { reactive } from 'vue';

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
    <div class="col-md-2 mb-2">
      <select @change="e => estado.filtro = e.target.value" class="form-control">
        <option value="+">Adição</option>
        <option value="-">Subtração</option>
        <option value="x">Multiplicação</option>
        <option value="÷">Divisão</option>
      </select>
    </div>
    <form>
      <input type="number" placeholder="Insira o primeiro número" class="form-control"
        @keyup="e => estado.valorA = e.target.value">
      <h5 class="text-center">{{ estado.filtro }}</h5>
      <input type="number" placeholder="Insira o primeiro número" class="form-control"
        @keyup="e => estado.valorB = e.target.value">
      <div class="alert alert-info mt-2" role="alert">
        Resuldado: {{ getOperatoresFiltros() }}
      </div>
    </form>
  </div>
</template>

<style scoped></style>
