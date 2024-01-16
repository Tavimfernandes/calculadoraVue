<script setup>
const props = defineProps([''])
</script>

<template>
    <div class="card-footer">
        <h5>Resultado:</h5>
        <span class="form-text">{{ getResultado() }}</span>
    </div>
</template>