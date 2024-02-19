<script setup>
import WelcomeMsg from './components/WelcomeMsg.vue';
import Calculator from './components/Calculator.vue';
</script>

<template>
  <div class="container">
    <header>
      <WelcomeMsg msg="Selamat Datang di Program Kalkulator" />
    </header>

    <main>
      <Calculator />
    </main>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
}
header {
  margin-bottom: 32px;
}
main {
  display: flex;
  justify-content: center;
}
</style>
