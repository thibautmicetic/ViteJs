<script lang="ts">
import {defineComponent} from "vue";

export default defineComponent({
  data() {
    return {
      count: 0,
    };
  },
  methods: {
    incrementCount() {
      this.count++;
    }
  }
});
</script>

<template>
  <h1>Ceci est un composant</h1>

  <p>{{count}}</p>

  <button @click="incrementCount()">Clicker</button>
</template>

<style scoped>
h1 {
  color: red;
}
</style>