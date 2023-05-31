<script setup>
import { RouterLink } from 'vue-router'
</script>

<template>
  <nav>
  <RouterLink class="home" to="/">Promptly</RouterLink>
    <div class="links">
      <!-- <RouterLink to="/appfinder" v-slot="{ navigate }">
              <button @click="navigate">App Finder</button>
            </RouterLink> -->
      <a href="https://idc8nflfnud.typeform.com/to/HmgFptlu" target="_blank" class="button">App Finder</a>
      <RouterLink to="/database" v-slot="{ navigate }">
        <button @click="navigate">Database</button>
      </RouterLink>
    </div>
  </nav>
</template>

<style scoped>
nav {
  background: #4d2986;
  height: 56px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-family: 'Rubik', sans-serif;
  box-shadow: 0px 2px 2px gray;
}

.home {
  font-size: 24px;
  color: white;
  padding-left: 15px;
  font-weight: bold;
}

@media (min-width: 480px) {
  nav {
    height: 64px;
    gap: 20px;
  }

  button {
    height: 64px;
    width: 120px;
  }

  .home {
    padding-left: 30px;
    font-size: 30px;
  }

  button:hover,
  .button:hover {
    background: #59309c;
  }

  .links {
    padding-right: 15px;
  }

  button {
    background: #4d2986;
    color: white;
    border: 0px;
    cursor: pointer;
    font-family: 'Rubik', sans-serif;
    font-size: 18px;
  }

  .button {
    padding: 21px 21px;
    color: white;
    font-family: 'Rubik', sans-serif;
    font-size: 18px;
  }
}
</style>
