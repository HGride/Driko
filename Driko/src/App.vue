<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="@/assets/logo.png" width="50" height="50" />
    <nav>
      <RouterLink to="/">Home</RouterLink>
      <RouterLink to="/about">Drinks</RouterLink>
    </nav>
  </header>

  <RouterView />
</template>

<style scoped>
header {
  line-height: 1.5;
  height: 70px;
  position: relative;
  inset: 0 0 auto 0;
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  padding: 2rem;
  background-color: #12011d;
  z-index: 5;
}

.logo {
  display: block;
}

nav {
  display: flex;
  height: 100%;
  align-items: center;
  justify-content: center;
}

</style>
