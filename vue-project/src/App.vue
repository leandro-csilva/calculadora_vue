<script setup>
import { reactive } from 'vue';

  const estado = reactive ({
      num1: 0,
      num2: 0,
      resultado: 0
    })

    function somar() {
      estado.resultado = estado.num1 + estado.num2
    }

    function subtrair() {
      estado.resultado = estado.num1 - estado.num2
    }

    function multiplicar() {
      estado.resultado = estado.num1 * estado.num2
    }

    function dividir() {
      estado.resultado = estado.num1 / estado.num2
    }

</script>

<template>
  <h1>Calculadora</h1>

  <form >
    <input @keyup="evento => estado.num1 = evento.target.value" type="number" v-model="num1">
    <input @keyup="evento => estado.num2 = evento.target.value" type="number" v-model="num2">

    <select class="form-control" name="" id="">
      <option @select="somar" value="somar">+</option>
      <option @select="subtrair" value="subtrair">-</option>
      <option @select="multiplicar" value="multiplicar">*</option>
      <option @select="dividir" value="dividir">/</option>
    </select>
    <p>Resultado: {{ estado.resultado }}</p>
  </form>
</template>

<style scoped>

</style>
