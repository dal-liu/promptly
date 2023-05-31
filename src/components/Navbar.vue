<script setup>
import { RouterLink } from 'vue-router'
import { ref } from 'vue'

const menuClicked = ref(false)
const clickMenu = () => menuClicked.value = !menuClicked.value
</script>

<template>
  <nav>
    <p class="home">Promptly</p>
    <div class="navlinks">
      <RouterLink to="/" v-slot="{ navigate }">
        <button @click="navigate">Home</button>
      </RouterLink>
      <a href="https://idc8nflfnud.typeform.com/to/HmgFptlu" target="_blank">
        <div class="button">App Finder</div>
      </a>
      <RouterLink to="/database" v-slot="{ navigate }">
        <button @click="navigate">Database</button>
      </RouterLink>
    </div>
    <div class="hamburger" @click="clickMenu" v-if="!menuClicked">
      <span class="bar"></span>
      <span class="bar"></span>
      <span class="bar"></span>
    </div>
    <div class="close" @click="clickMenu" v-if="menuClicked">&#10005;</div>
  </nav>
  
  <div class="shade" v-if="menuClicked" @click="clickMenu"></div>
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
  margin-left: 15px;
  font-weight: bold;
}

.navlinks {
  display: none;
}

.hamburger {
  cursor: pointer;
  margin-right: 15px;
}

.close {
  cursor: pointer;
  margin-right: 16px;
  color: white;
  font-size: 28px;
  font-family: 'Rubik', sans-serif;
  font-weight: bold;
}

.bar {
  display: block;
  width: 25px;
  height: 3px;
  margin: 5px auto;
  background-color: white;
  border-radius: 2px;
}

.shade {
  position: absolute;
  height: 100%;
  width: 100%;
  z-index: 1000;
}

@media (min-width: 480px) {
  nav {
    height: 64px;
    gap: 20px;
  }

  .home {
    margin-left: 30px;
    font-size: 30px;
  }

  button,
  .button {
    height: 64px;
    width: 100px;
    background: #4d2986;
    color: white;
    border: 0px;
    cursor: pointer;
    font-family: 'Rubik', sans-serif;
    font-size: 18px;
  }

  .button {
    display: flex;
    align-items: center;
    justify-content: center;
  }

  button:hover,
  .button:hover {
    background: #59309c;
  }

  .navlinks {
    padding-right: 15px;
    display: flex;
  }

  .hamburger {
    display: none;
  }
}
</style>
