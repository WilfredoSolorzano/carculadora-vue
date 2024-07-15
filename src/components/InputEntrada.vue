<script setup>
import { defineProps, defineEmits } from 'vue';

const props = defineProps(['num1']);
const emit = defineEmits(['update:num1']);

function updateNum1(event) {
  emit('update:num1', Number(event.target.value));
}
</script>

<template>
  <div class="col">
    <input v-model.number="props.num1" type="number" class="form-control" placeholder="Número 1" @input="updateNum1" />
  </div>
</template>