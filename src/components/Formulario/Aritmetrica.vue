<script setup>
    const props = defineProps(['estadoFiltro'])
</script>
<template>
    <div class="col-md-2 mb-2">
        <select @change="props.estadoFiltro" class="form-control">
            <option value="+">Adição</option>
            <option value="-">Subtração</option>
            <option value="x">Multiplicação</option>
            <option value="÷">Divisão</option>
        </select>
    </div>
</template>