<script setup lang="ts">
import {reactive, computed, ref} from 'vue';
import Card from "./Card.vue";

const search = ref("");

const author = reactive({
  name: 'Jonh Doe',
  books: [
      'Vue 2 - Brosseau',
      'Vue 3 - Test',
      'Vue 4 - Démo',
  ]
});

const filteredBooks = computed(() => {
  if(search.value != ""){
    return author.books.filter(it => it.includes(search.value));
  } else {
    return author.books;
  }
})

const publishedBooksMessage = computed(() => {
  return filteredBooks.value.length;
})
</script>

<template>
  <p>
    Auteur: {{author.name}}
  </p>

  <input type="text" v-model="search" placeholder="Rechercher un livre" />

  <div v-for="book in filteredBooks" :key="book">
    <Card :book=book></Card>
    <Button color="red" :label="'Supprimer'"></Button>
  </div>


  <p>
    Nombre de livre : <span>{{ publishedBooksMessage }}</span>
  </p>
</template>