<script setup>
const props = defineProps(['calculaOperador'])
</script>


<template>
    <div class="card-body d-flex">
        <label for="operadorAritmetico" class="me-2">Operador :</label>
        <select v-model="estado.operadorAritmetico" class="form-control w-25">
            <option value="adicao">+ Adição</option>
            <option value="subtracao">- Subtração</option>
            <option value="multiplicacao">* Multiplicação</option>
            <option value="divisao">/ Divisão</option>
        </select>
    </div>
</template>