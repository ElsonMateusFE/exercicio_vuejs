<script setup>
    const props = defineProps(['estadoA','estadoFiltro', 'estadoB', 'operatoresFiltros'])
</script>
<template>
    <form>
        <input type="number" placeholder="Insira o primeiro número" class="form-control"
            @keyup="props.estadoA">
        <h5 class="text-center">{{ props.estadoFiltro }}</h5>
        <input type="number" placeholder="Insira o primeiro número" class="form-control"
            @keyup="props.estadoB">
        <div class="alert alert-info mt-2" role="alert">
            Resuldado: {{ props.operatoresFiltros }}
        </div>
    </form>
</template>