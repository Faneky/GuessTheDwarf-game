<script setup>
import Game from './components/Game.vue'
import Rules from './components/Rules.vue'
import { ref, computed} from 'vue'

alert('If you want to know name and age, look in console')



const routes = {
  '/': Game,
  '/rules': Rules,
}
const currentPath = ref(window.location.hash)

window.addEventListener('hashchange', () => {
  currentPath.value = window.location.hash
})

const currentView = computed(() => {
  return routes[currentPath.value.slice(1) || '/'] || NotFound
})

</script>

<template>
  <header>
    <div class="links-container">
    <a class="game" href="#/">Game</a>
    <a class="rules" href="#/rules">Rules</a>
  </div>
  </header>
  <main>
    <component :is="currentView" />
  </main>
</template>

<style scoped>
.links-container {
  display: flex;
  justify-content: center;
}
.links-container > *{
  margin-right: 2em;
  color: #fff;
}
.links-container > *:last-child{
  margin-right: 0em;
}
</style>
