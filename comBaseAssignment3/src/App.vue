<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
// import HelloWorld from './components/EventCard.vue/index.js'

import { ref } from 'vue'

const pageSize = ref(2)

</script>

<template>
  <div id="layout">
    <header>
      <div class="wrapper">
        <nav>
          <RouterLink :to="{ name: 'event-list-view' }">Event</RouterLink> |
          <RouterLink :to="{ name: 'about' }">About</RouterLink>
        </nav>

        <div class="page-size">
          <span>Page Size: </span>
          <button @click="pageSize = 1">1</button>
          <button @click="pageSize = 2">2</button>
          <button @click="pageSize = 3">3</button>
          <button @click="pageSize = 4">4</button>
        </div>

      </div>
    </header>
    <RouterView :page-size="pageSize" />
  </div>
</template>

<style>

#layout {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

h2 {
  font-size: 20px;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}

.page-size button {
  margin: 0 4px;
}
</style>
