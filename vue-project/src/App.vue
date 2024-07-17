<script setup>
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
    <input type="number" v-model="num1">
    <input type="number" v-model="num2">

    {{ estado.resultado }}
    <select @change="" class="form-control" name="" id="">
      <option @click="somar" value="somar">+</option>
      <option @click="subtrair" value="subtrair">-</option>
      <option @click="multiplicar" value="multiplicar">*</option>
      <option @click="dividir" value="dividir">/</option>
    </select>
    <p>Resultado: {{ resultado }}</p>
  </form>
</template>

<style scoped>

</style>
