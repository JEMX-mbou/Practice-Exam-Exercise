<template>
  <header>
    <nav class="navbar jc-center">
      <div class="menu-icon" ref="icon" @click="mobMenu()"><div class="inner"></div></div>
      <div class="nav-background" :style="`opacity:${bg.opacity}`"></div>
      <ul ref="menu">
        <li><a href="#service">Services</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
    </nav>
  </header>
</template>

<script setup>
import { onMounted, reactive, ref } from 'vue'

const bg = reactive({ opacity: 0 })

const menu = ref()
const icon = ref()

function mobMenu() {
  menu.value.classList.toggle('is-active')
  icon.value.classList.toggle('is-active')
}

onMounted(() => {
  window.addEventListener('scroll', () => {
    switch (true) {
      case window.pageYOffset == 0:
        bg.opacity = 0
        break
      case window.pageYOffset <= 10:
        bg.opacity = 0.1
        break
      case window.pageYOffset <= 20:
        bg.opacity = 0.2
        break
      case window.pageYOffset <= 30:
        bg.opacity = 0.3
        break
      case window.pageYOffset <= 40:
        bg.opacity = 0.4
        break
      case window.pageYOffset <= 50:
        bg.opacity = 0.5
        break
      case window.pageYOffset <= 60:
        bg.opacity = 0.6
        break
      case window.pageYOffset <= 70:
        bg.opacity = 0.7
        break
      case window.pageYOffset <= 80:
        bg.opacity = 0.8
        break
      case window.pageYOffset <= 90:
        bg.opacity = 0.9
        break
      default:
        bg.opacity = 1
        break
    }
  })
})
</script>

<style lang="scss" scoped>
nav.navbar {
  position: fixed;
  top: 0;
  width: 100%;
  background-color: transparent;
  border-bottom: none;

  .nav-background {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 300%;
    background: linear-gradient(0deg, #1110 0%, #111f 80%, #111f 100%);
    pointer-events: none;
    z-index: 0;
  }

  .menu-icon {
    padding: 1rem 0.5rem;
    z-index: 1;
    .inner,
    .inner::before,
    .inner::after {
      background-color: #fff;
    }

    &.is-active {
      .inner {
        background-color: transparent;
      }
      .inner::before,
      .inner::after {
        background-color: #222;
      }
    }
  }

  a {
    font-weight: bold;
    color: #fff;
  }

  ul.is-active a {
    color: #222;
  }
}
</style>
