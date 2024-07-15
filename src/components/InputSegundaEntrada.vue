<script setup>
import { defineProps, defineEmits } from 'vue';

const props = defineProps(['num2', 'operation']);
const emit = defineEmits(['update:num2', 'update:operation']);

function updateNum2(event) {
  emit('update:num2', Number(event.target.value));
}

function updateOperation(event) {
  emit('update:operation', event.target.value);
}
</script>

<template>
  <div>
    <div class="col">
      <select v-model="props.operation" class="form-select" @change="updateOperation">
        <option value="add">+</option>
        <option value="subtract">-</option>
        <option value="multiply">*</option>
        <option value="divide">/</option>
      </select>
    </div>
    <div class="col">
      <input v-model.number="props.num2" type="number" class="form-control" placeholder="Número 2" @input="updateNum2" />
    </div>
  </div>
</template>