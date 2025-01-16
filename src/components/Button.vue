<script setup lang="ts">
import { defineProps } from "vue";

defineProps<{
  label: {
    type: String,
    required: true,
  },
  color: {
    type: String,
  },
}>();
</script>

<template>
  <button :label="label" color="red">{{label}}</button>
</template>