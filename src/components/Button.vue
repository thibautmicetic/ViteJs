<script setup lang="ts">
import { defineProps } from "vue";

const props = defineProps({
  label: {
    type: String,
    required: true,
  },
  color: {
    type: String,
    required: true,
  },
});
</script>

<template>
  <button :class="color" color="red"> {{ label }} </button>
</template>