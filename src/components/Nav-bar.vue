<template>
  <div class="container">
    <nav class="navbar">
      <div>
        <a class="navbar__logo" href="#"> LOGO </a>

        <div class="navbar__links">
          <ul class="navbar__links-list">
            <li><a class="navbar__links-list--active" href="#">Home</a></li>
            <li><a href="#">About</a></li>
            <li><a href="#">Skills</a></li>
            <li><a href="#">Projects</a></li>
            <li><a href="#">Blogs</a></li>
            <li><a href="#" target="_blank" rel="noopener" download="">Download CV</a></li>
            <li>
              <div><a href="#">dark</a></div>
            </li>
          </ul>
        </div>
      </div>
    </nav>
  </div>
</template>

<script>
export default {
  setup() {
    return {}
  }
}
</script>

<style lang="scss" scoped>
.container {
  display: flex;
  justify-content: space-between;
  box-shadow: 0 3px 15px #16297c1a;
  background-color: #f8f9fa;
}
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin: 0 auto;

  height: 100px;

  &__logo {
    img {
      display: block;
    }
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
</style>
