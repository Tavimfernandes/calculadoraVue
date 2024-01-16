<script setup>
const props = defineProps(['primeiroNumero', 'segundoNumero',])
</script>

<template>
    <div class="card-header d-flex">
        <input v-model="props.primeiroNumero" type="number" class="form-control w-25 me-2"
            placeholder="Digite o primeiro número:" id="numeroA">
        <input v-model="props.segundoNumero" type="number" class="form-control w-25"
            placeholder="Digite o segundo número:" id="numeroB">
    </div>
</template>