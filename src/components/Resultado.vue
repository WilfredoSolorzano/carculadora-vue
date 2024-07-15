<script setup>
import { defineProps } from 'vue';

const props = defineProps(['result']);
</script>

<template>
  <p class="alert alert-info">Resultado: {{ props.result }}</p>
</template>