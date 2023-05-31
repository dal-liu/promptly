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
        <button @click="navigate" class="navbutton">Home</button>
      </RouterLink>
      <a href="https://idc8nflfnud.typeform.com/to/HmgFptlu" target="_blank">
        <div class="navbutton" id="a">App Finder</div>
      </a>
      <RouterLink to="/database" v-slot="{ navigate }">
        <button @click="navigate" class="navbutton">Database</button>
      </RouterLink>
    </div>

    <div class="hamburger" @click="clickMenu" v-if="!menuClicked">
      <span class="bar"></span>
      <span class="bar"></span>
      <span class="bar"></span>
    </div>
    <div class="close" @click="clickMenu" v-if="menuClicked">&#10005;</div>
  </nav>

  <Transition name="slide" mode="default">
    <div class="dropmenu" v-if="menuClicked" @click="clickMenu">
      <RouterLink to="/" v-slot="{ navigate }">
        <button @click="navigate" class="dropbutton">Home</button>
      </RouterLink>
      <a href="https://idc8nflfnud.typeform.com/to/HmgFptlu" target="_blank">
        <div class="dropbutton" id="a">App Finder</div>
      </a>
      <RouterLink to="/database" v-slot="{ navigate }">
        <button @click="navigate" class="dropbutton">Database</button>
      </RouterLink>
    </div>
  </Transition>

  <Transition name="fade" mode="default">
    <div class="shade" v-if="menuClicked" @click="clickMenu"></div>
  </Transition>
</template>

<style scoped>
nav {
  background: #4d2986;
  height: 56px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-family: 'Rubik', sans-serif;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 3;
  touch-action: none;
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
  margin-right: 15px;
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

.dropmenu {
  display: flex;
  width: 100%;
  position: fixed;
  z-index: 2;
  flex-direction: column;
  touch-action: none;
  background-color: #4d2986;
  top: 56px;
}

.dropbutton {
  height: 56px;
  width: 100%;
  background-color: #4d2986;
  border: none;
  outline: none;
  color: white;
  font-family: 'Rubik', sans-serif;
  font-size: 18px;
}

.dropbutton:hover {
  background: #59309c;
}

#a {
  display: flex;
  align-items: center;
  justify-content: center;
}

.shade {
  position: fixed;
  height: 100%;
  width: 100%;
  z-index: 1;
  opacity: 0.5;
  background-color: black;
  touch-action: none;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

.fade-enter-active,
.fade-leave-active {
  transition: 0.2s opacity ease;
}

.slide-enter-from,
.slide-leave-to {
  transform: translateY(-224px);
}

.slide-enter-active,
.slide-leave-active {
  transition: 0.4s;
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

  .navbutton {
    height: 64px;
    width: 100px;
    background: #4d2986;
    color: white;
    border: 0px;
    cursor: pointer;
    font-family: 'Rubik', sans-serif;
    font-size: 18px;
  }

  .navbutton:hover {
    background: #59309c;
  }

  .navlinks {
    padding-right: 15px;
    display: flex;
  }

  .hamburger,
  .close,
  .dropmenu,
  .shade {
    display: none;
  }
}
</style>
