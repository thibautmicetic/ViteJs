<script setup lang="ts">
import {ref} from 'vue';
import {useDark, useMouse, useToggle} from '@vueuse/core'
import Author from "./components/Author.vue";
import Old from "./components/Old.vue";

// tracks mouse position
const { x, y } = useMouse()

// is user prefers dark theme
const isDark = useDark();
const toggleDark = useToggle(isDark);

const count = ref(0);
const msg = ref('TP3');
const input = ref('Thibaut');
</script>

<template>
  {{ x }}, {{ y }}
  <div v-if="isDark">Dark mode</div>
  <div v-else>Light mode</div>

  <button @click="toggleDark()">Toggle</button>

  <h1>{{msg}}</h1>

  <div class="card">
    <button type="button" @click="count--">--</button>
    <button type="button">{{ count }}</button>
    <button type="button" @click="count++">++</button>
  </div>

  <div class="card">
    <h2>hello {{ input }}</h2>
    <input v-model="input" />
  </div>

  <div>
    <p>UI BONCHOUR</p>
  </div>

  <Author></Author>
  <Old></Old>

  <div class="card">
    <div class="card-body">
      <p>La brique ne sait pas coder</p>
      <slot></slot>
    </div>
  </div>
</template>

<style scoped>
.card {
  background: #e6e2e2;
  border: 1px solid #ccc;
  border-radius: 10px;
  margin: 10px;
}
</style>
