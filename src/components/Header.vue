<script setup>
import { ref } from 'vue'

const isOpened = ref(false)

const toggleMenu = () => {
  isOpened.value = !isOpened.value
}

</script>

<template>
  <header class="header">
    <nav class="nav-desktop">
      <router-link to="/">
            <img src="../assets/logo.svg" class="logo" alt="logo" />
      </router-link>
      <div class="nav-links">
        <router-link to="/" class="nav-link">Home</router-link>
        <router-link to="/about" class="nav-link">About</router-link>
        <router-link to="/skills" class="nav-link">Skills</router-link>
        <router-link to="/projects" class="nav-link">Projects</router-link>
        <router-link to="/contacts" class="nav-link">Contact</router-link>
      </div>
      <button class="menu-toggle" @click="toggleMenu" :class="{ 'opened': isOpened }" aria-label="Toggle Menu">
        <span></span>
        <span></span>
        <span></span>
      </button>
    </nav>
    <nav class="nav-mobile" :class="{ 'opened': isOpened }">
      <router-link to="/" @click="toggleMenu" class="nav-link">Home</router-link>
      <router-link to="/about" @click="toggleMenu" class="nav-link">About</router-link>
      <router-link to="/skills" @click="toggleMenu" class="nav-link">Skills</router-link>
      <router-link to="/projects" @click="toggleMenu" class="nav-link">Projects</router-link>
      <router-link to="/contacts" @click="toggleMenu" class="nav-link">Contact</router-link>
    </nav>
  </header>

</template>

<style lang="scss" scoped>

.header {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.05);
  z-index: 10;
}

.nav-desktop {
  max-width: 1200px;
  margin: 0 auto;
  padding: 1.5rem 2rem;
  display: flex;
  justify-content: space-between;
  align-items: center;

  .logo {
    height: 5em;
    padding: 1em;
    transition: transform var(--transition-speed) ease;

    &:hover {
      transform: scale(1.05);
    }
  }

  .nav-links {
    display: flex;
    gap: 2.5rem;

    .nav-link {
      color: var(--text-color);
      text-decoration: none;
      font-weight: 600;
      font-size: 1.1em;
      padding: 0.6rem 1.2rem;
      position: relative;
      overflow: hidden;
      transition: all var(--transition-speed) ease;

      &:hover {
        transform: scale(1.05);
        color: var(--hovered-color);
      }

      &.router-link-active {
        color: var(--active-color);
      }
    }
  }
}

.menu-toggle {
  display: none;
  background: none;
  border: none;
  cursor: pointer;
  padding: 0.5rem;
  z-index: 100;

  span {
    display: block;
    width: 28px;
    height: 3px;
    background: var(--text-color); /* Fixed to use primary color */
    margin: 5px 0;
    border-radius: 2px;
    transition: all var(--transition-speed) ease;
  }

  &.opened {
    span {
      &:first-child {
        transform: rotate(45deg) translate(6px, 6px);
      }
      &:nth-child(2) {
        opacity: 0;
      }
      &:last-child {
        transform: rotate(-45deg) translate(6px, -6px);
      }
    }
  }
}

.nav-mobile {
  display: none;
  flex-direction: column;
    background: rgb(0 15 49);
  backdrop-filter: blur(12px);
  padding: 2rem;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  height: 100vh;
  transform: translateX(100%);
  transition: transform var(--transition-speed) ease;
  z-index: 90;

  &.opened {
    transform: translateX(0);
  }

  .nav-link {
    padding: 0.8em 1rem;
    color: var(--text-color);
    text-decoration: none;
    font-weight: 600;
    font-size: 1.3em;
    border-radius: var(--border-radius);
    transition: all var(--transition-speed) ease;
        margin-top: 50px;
    &:hover, &.router-link-active {
      color: var(--primary-color);
      background: rgba(79, 70, 229, 0.15);
      transform: translateX(5px);
    }
  }
}

@keyframes spin {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}

@media (max-width: 768px) {
  .nav-desktop {
    padding: 1rem 1.5rem;

    .nav-links {
      display: none;
    }

    .menu-toggle {
      display: block;
    }
  }

  .nav-mobile {
    display: flex;
  }


}
</style>