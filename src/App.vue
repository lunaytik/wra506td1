<script setup>
import { RouterLink, RouterView } from 'vue-router'
import { computed } from 'vue'
import Component from './components/Component.vue'

const data = {
  symfony: '15',
  integration: '20',
  reseau: '12'
}

const note1 = 15
const note2 = 20
const note3 = 12


const moy = computed(() => {
  return ((note1 + note2 + note3)/3).toFixed(2);
})

</script>

<template>
  <header>
    <div class="wrapper">
      <ul>
        <li v-for="(note, matiere) in data">{{ matiere.toUpperCase() }} : {{ note }}</li>
      </ul>

      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
      </nav>

      <h1>Moyenne de : {{ moy }}</h1>
      <Component></Component>
    </div>
  </header>

  <RouterView />
</template>

<style scoped>
  h1 {
    font-style: italic;
  }
</style>