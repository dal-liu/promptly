<script setup>
import Navbar from './components/Navbar.vue'
import { RouterView } from 'vue-router'
</script>

<template>
  <header>
    <Navbar />
  </header>

  <main>
    <RouterView v-slot="{ Component, route }">
      <Transition name="fade" mode="out-in">
        <div :key="route.name">
          <component :is="Component" />
        </div>
      </Transition>
    </RouterView>
  </main>

  <footer>
    <div class="copyright">
      Copyright &copy; 2023 Daniel Liu, AJ Liss, Angela Guan, George Moseley
    </div>
  </footer>
</template>

<style>
main {
  padding-bottom: 100px;
  will-change: opacity, transform;
  margin-top: 56px;
}

footer {
  background-color: #f2f2f2;
  color: #737373;
  height: 100px;
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
}

.copyright {
  font-family: 'Rubik', sans-serif;
  font-size: 12px;
  padding: 25px;
  text-align: center;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

.fade-enter-active,
.fade-leave-active {
  transition: 0.3s opacity ease-out;
}

@media (min-width: 480px) {
  main {
    margin-top: 60px;
  }
}
</style>
