<script setup>
import { reactive } from 'vue';
import Resultado from './components/Resultado.vue';
import Calculadora from './components/Calculadora.vue';
import Operador from './components/Operador.vue';

const estado = reactive({
  operadorAritmetico: '',
  resultado: '',
  numeros: {
    numeroA: 0,
    numeroB: 0
  }
})

const getOperadorAdicao = () => {
  return estado.numeros.numeroA + estado.numeros.numeroB;
}

const getOperadorSubtracao = () => {
  return estado.numeros.numeroA - estado.numeros.numeroB;
}

const getOperadorMulti = () => {
  return estado.numeros.numeroA * estado.numeros.numeroB;
}

const getOperadorDivisao = () => {
  return estado.numeros.numeroA / estado.numeros.numeroB;
}

const getResultado = () => {
  switch (estado.operadorAritmetico) {
    case 'adicao':
      return getOperadorAdicao();
    case 'subtracao':
      return getOperadorSubtracao();
    case 'multiplicacao':
      return getOperadorMulti();
    case 'divisao':
      return getOperadorDivisao();
    default:
      return estado.resultado;
  }
}

</script>

<template>
  <div class="container">
    <header class="p-5 mb-4 mt-4 bg-light rounded-3">
      <h1>Calculadora Aritmética</h1>
      <hr />
      <p>Digite um número em cada campo númerico, selecione um operador e veja o resultado!!!</p>
    </header>
    <div class="card">
      <div class="card-header d-flex">
        <input v-model="estado.numeros.numeroA" type="number" class="form-control w-25 me-2"
          placeholder="Digite o primeiro número:" id="numeroA">
        <input v-model="estado.numeros.numeroB" type="number" class="form-control w-25" placeholder="Digite o segundo número:"
          id="numeroB">
      </div>
      <div class="card-body d-flex">
        <label for="operadorAritmetico" class="me-2">Operador :</label>
        <select v-model="estado.operadorAritmetico" class="form-control w-25">
          <option value="adicao">+ Adição</option>
          <option value="subtracao">- Subtração</option>
          <option value="multiplicacao">* Multiplicação</option>
          <option value="divisao">/ Divisão</option>
        </select>
      </div>
      <div class="card-footer">
        <h5>Resultado:</h5>
        <span class="form-text">{{ getResultado() }}</span>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
