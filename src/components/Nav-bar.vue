<template>
  <div class="container">
    <nav class="navbar">
      <a class="navbar__logo" href="#">
        <img src="../assets/favicon-full.png" alt="favicon" height="70px" width="124px" />
      </a>

      <div class="navbar__links" :class="{ 'is-active': navOpen }">
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
import { ref, onMounted } from 'vue'

export default {
  setup() {
    const navItems = ref([
      { name: 'Home', href: '#home', active: true },
      { name: 'About', href: '#about', active: false },
      { name: 'Skills', href: '#skills', active: false },
      { name: 'Projects', href: '#projects', active: false },
      { name: 'Contact', href: '#contact', active: false }
    ])
    const navOpen = ref(false)

    const toggleNav = () => {
      navOpen.value = !navOpen.value
    }

    const setActive = (name) => {
      navItems.value.forEach((item) => {
        item.active = item.name === name
      })
      navOpen.value = false
    }

    onMounted(() => {
      window.addEventListener('scroll', () => {
        const scrollPosition = window.scrollY + window.innerHeight / 3
        navItems.value.forEach((item) => {
          const section = document.querySelector(item.href)
          if (section) {
            const top = section.offsetTop
            const bottom = top + section.offsetHeight
            if (scrollPosition >= top && scrollPosition <= bottom) {
              setActive(item.name)
            }
          }
        })
      })
    })

    return { navItems, setActive, navOpen, toggleNav }
  }
}
</script>

<style lang="scss" scoped>
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
  width: 60vw;
  justify-content: space-between;

  &__logo {
    display: flex;
    justify-content: space-between;

    @media screen and (max-width: 860px) {
      display: flex;
      justify-content: space-between;
    }
  }

  &__toggle {
    display: none;
    cursor: pointer;

    @media screen and (max-width: 860px) {
      display: block;
    }
  }

  &__hamburger {
  }

  &__toggle:focus .navbar__hamburger,
  &__toggle:hover .navbar__hamburger {
    background-color: #12b886;
  }

  &__links {
    display: flex;

    @media screen and (max-width: 860px) {
      display: none;
      position: absolute;
      top: 100%;
      left: 0;
      width: 100%;
      flex-direction: column;
      background-color: #f8f9fa;

      &.is-active {
        display: flex;
        justify-content: center;
      }
    }
  }

  &__links-list {
    display: flex;
    gap: 1rem;
    list-style: none;

    &--active {
      color: #12b886 !important;
      border-color: #12b886 !important;
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

.bm-burger-button {
  position: fixed;
  width: 36px;
  height: 30px;
  left: 36px;
  top: 36px;
  cursor: pointer;
}
.bm-burger-bars {
  background-color: #373a47;
}
.line-style {
  position: absolute;
  height: 20%;
  left: 0;
  right: 0;
}
.cross-style {
  position: absolute;
  top: 12px;
  right: 2px;
  cursor: pointer;
}
.bm-cross {
  background: #bdc3c7;
}
.bm-cross-button {
  height: 24px;
  width: 24px;
}
.bm-menu {
  height: 100%; /* 100% Full-height */
  width: 0; /* 0 width - change this with JavaScript */
  position: fixed; /* Stay in place */
  z-index: 1000; /* Stay on top */
  top: 0;
  left: 0;
  background-color: rgb(63, 63, 65); /* Black*/
  overflow-x: hidden; /* Disable horizontal scroll */
  padding-top: 60px; /* Place content 60px from the top */
  transition: 0.5s; /*0.5 second transition effect to slide in the sidenav*/
}

.bm-overlay {
  background: rgba(0, 0, 0, 0.3);
}
.bm-item-list {
  color: #b8b7ad;
  margin-left: 10%;
  font-size: 20px;
}
.bm-item-list > * {
  display: flex;
  text-decoration: none;
  padding: 0.7em;
}
.bm-item-list > * > span {
  margin-left: 10px;
  font-weight: 700;
  color: white;
}
</style>
