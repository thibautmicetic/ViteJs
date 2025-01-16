<script setup lang="ts">
import {defineProps} from "vue";

  defineProps<{ book: string }>()
</script>

<template>
  <div class="card">
    <div class="card-body">
      {{book}}
      <slot>
      </slot>
    </div>
  </div>
</template>