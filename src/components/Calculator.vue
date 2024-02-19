<script setup>
import ButtonCalculator from './ButtonCalculator.vue';
import { ref } from 'vue';

const inputText = ref('');

const onButtonClick = (c) => {
  switch (c) {
    case '=':
      try {
        const res = eval(inputText.value);
        inputText.value = res;
      } catch (err) {
        alert('Error: cannot evaluate expression');
      }
      break;
    case 'AC':
      inputText.value = '';
      break;
    case 'x':
      inputText.value += '*';
      break;
    default:
      inputText.value += c;
      break;
  }
};
</script>

<template>
  <div class="container">
    <header>
      <input v-bind:value="inputText" />
    </header>

    <main>
      <table>
        <tr>
          <td width="25%">
            <ButtonCalculator
              class="btn"
              nilai="+"
              @btn-click="onButtonClick"
            />
          </td>
          <td width="25%">
            <ButtonCalculator
              class="btn"
              nilai="-"
              @btn-click="onButtonClick"
            />
          </td>
          <td width="25%">
            <ButtonCalculator
              class="btn"
              nilai="x"
              @btn-click="onButtonClick"
            />
          </td>
          <td width="25%">
            <ButtonCalculator
              class="btn"
              nilai="/"
              @btn-click="onButtonClick"
            />
          </td>
        </tr>
        <tr>
          <td>
            <ButtonCalculator
              class="btn"
              nilai="7"
              @btn-click="onButtonClick"
            />
          </td>
          <td>
            <ButtonCalculator
              class="btn"
              nilai="8"
              @btn-click="onButtonClick"
            />
          </td>
          <td>
            <ButtonCalculator
              class="btn"
              nilai="9"
              @btn-click="onButtonClick"
            />
          </td>
          <td rowspan="4">
            <ButtonCalculator
              class="btn btn-eq"
              nilai="="
              @btn-click="onButtonClick"
            />
          </td>
        </tr>
        <tr>
          <td>
            <ButtonCalculator
              class="btn"
              nilai="4"
              @btn-click="onButtonClick"
            />
          </td>
          <td>
            <ButtonCalculator
              class="btn"
              nilai="5"
              @btn-click="onButtonClick"
            />
          </td>
          <td>
            <ButtonCalculator
              class="btn"
              nilai="6"
              @btn-click="onButtonClick"
            />
          </td>
        </tr>
        <tr>
          <td>
            <ButtonCalculator
              class="btn"
              nilai="1"
              @btn-click="onButtonClick"
            />
          </td>
          <td>
            <ButtonCalculator
              class="btn"
              nilai="2"
              @btn-click="onButtonClick"
            />
          </td>
          <td>
            <ButtonCalculator
              class="btn"
              nilai="3"
              @btn-click="onButtonClick"
            />
          </td>
        </tr>
        <tr>
          <td>
            <ButtonCalculator
              class="btn"
              nilai="0"
              @btn-click="onButtonClick"
            />
          </td>
          <td>
            <ButtonCalculator
              class="btn"
              nilai="."
              @btn-click="onButtonClick"
            />
          </td>
          <td>
            <ButtonCalculator
              class="btn"
              nilai="AC"
              @btn-click="onButtonClick"
            />
          </td>
        </tr>
      </table>
    </main>
  </div>
</template>
<style scoped>
.container {
  display: flex;
  width: 400px;
  flex-direction: column;
}
header {
  display: flex;
}
input {
  flex-grow: 1;
  height: 80px;
  text-align: end;
  font-size: xx-large;
  color: white;
  background-color: #222222;
}
table {
  width: 100%;
}
td {
  height: 80px;
}
.btn {
  width: 100%;
  height: 100%;
  font-size: x-large;
}
.btn-eq {
  background-color: #ed8965;
}
</style>
