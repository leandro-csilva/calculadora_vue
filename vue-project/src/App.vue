<script setup>
import { reactive } from 'vue';

  const estado = reactive ({
      num1: 0,
      num2: 0,
      resultado: 0
    })

    function calcular(opcao) {
      switch (opcao) {
        case '+':
          estado.resultado = parseFloat(estado.num1) + parseFloat(estado.num2);
          break;
        
          case '-':
          estado.resultado = estado.num1 - estado.num2;
          break;

        case '*':
          estado.resultado = estado.num1 * estado.num2;
          break;

        case '/':
          estado.resultado = estado.num1 / estado.num2;
          break;

        default:
          console.error('Operação inválida');
      }
    }

</script>

<template>
    <h1>Calculadora</h1>

    <form >
      <input @keyup="estado.num1 = $event.target.value" type="number" placeholder="Número 1">
      <input @keyup="estado.num2 = $event.target.value" type="number" placeholder="Número 2">

      <select @change="calcular($event.target.value)" class="form-control" name="" id="">
        <option value="+">+</option>
        <option value="-">-</option>
        <option value="*">*</option>
        <option value="/">/</option>
      </select>
      <p>Resultado: {{ estado.resultado }}</p>
    </form>
</template>

<style scoped>


</style>
