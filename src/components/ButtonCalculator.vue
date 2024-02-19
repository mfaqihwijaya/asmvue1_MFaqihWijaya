<script setup>
const emit = defineEmits(['btn-click']);
const props = defineProps({
  nilai: {
    type: String,
    required: true,
  },
});
const clickCallback = () => {
  console.log(props.nilai);
  emit('btn-click', props.nilai);
};
</script>

<template>
  <button @click="clickCallback">
    {{ nilai }}
  </button>
</template>

<style scoped></style>
