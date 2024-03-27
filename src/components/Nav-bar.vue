<template>
  <div class="container">
    <nav class="navbar">
      <div class="navbar__logo">
        <a href="#"> LOGO </a>
      </div>

      <div class="navbar__links">
        <ul class="navbar__links-list">
          <li v-for="item in navItems" :key="item.name">
            <a
              :href="item.href"
              :class="{ 'navbar__links-list--active': item.active }"
              @click="setActive(item.name)"
            >
              {{ item.name }}
            </a>
          </li>
        </ul>
      </div>
    </nav>
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  setup() {
    const navItems = ref([
      { name: 'Home', href: '#', active: true },
      { name: 'About', href: '#about', active: false },
      { name: 'Skills', href: '#skills', active: false },
      { name: 'Projects', href: '#projects', active: false },
      { name: 'Questions', href: '#questions', active: false },
      { name: 'Download CV', href: '#', active: false }
    ])

    const setActive = (name) => {
      navItems.value.forEach((item) => {
        item.active = item.name === name
      })
    }

    return { navItems, setActive }
  }
}
</script>

<style lang="scss" scoped>
html {
  scroll-behavior: smooth;
}

.container {
  display: flex;
  justify-content: space-between;
  box-shadow: 0 3px 15px #16297c1a;
  background-color: #f8f9fa;
  position: fixed;
  top: 0;
  right: 0;
  left: 0;
  z-index: 5;
}

.navbar {
  display: flex;
  align-items: center;
  margin: 0 auto;
  height: 80px;

  &__logo {
    width: 100px;
  }

  &__links {
    &-list {
      display: flex;
      gap: 1rem;
      list-style: none;

      &--active {
        color: #12b886;
        border-color: #12b886;
      }

      li {
        a {
          font-family: Ubuntu, sans-serif;
          font-size: 18px;
          color: rgba(33, 37, 41, 0.75);
          font-weight: 700;
          text-decoration: none;
          padding: 8px 12px;
          border-radius: 20px;
          transition:
            background-color 0.3s,
            border-color 0.3s;
          border: 2px solid transparent;

          &:hover {
            color: #12b886;
            border-color: #12b886;
          }
        }
      }
    }
  }
}

@media screen and (min-width: 300px) and (max-width: 860px) {
  .navbar {
    &__links {
      display: none;
    }
  }
}
</style>
