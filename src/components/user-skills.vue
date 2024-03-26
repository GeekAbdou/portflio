<template>
  <div class="skills-header">
    <span>My Skills</span>
  </div>

  <div class="container">
    <div class="skills">
      <div class="skills__frontend">
        <div class="skills__frontend__heading">
          <img src="../assets/svg/frontend.svg" alt="frontend" />
          <h2>&lt;Frontend/&gt;</h2>
        </div>

        <div class="skills__frontend__list">
          <div class="skills__frontend__list--item">
            <img
              v-for="(item, index) in frontend"
              :src="`../src/assets/svg/${item}.svg`"
              :alt="item"
              :key="index"
            />
          </div>
        </div>
      </div>

      <div class="skills__others">
        <div class="skills__others__heading">
          <img src="../assets/svg/others.svg" alt="frontend" />
          <h2>Others</h2>
        </div>

        <div class="skills__others__list">
          <div class="skills__others__list--item">
            <img
              v-for="(item, index) in others"
              :src="`../src/assets/svg/${item}.svg`"
              :alt="item"
              :key="index"
            />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  setup() {
    const frontend = [
      'html',
      'css',
      'js',
      'ts',
      'react',
      'redux',
      'nextjs',
      'vuejs',
      'nuxtjs',
      'vuex',
      'bootstrap',
      'sass',
      'tailwind',
      'material',
      'jasmine',
      'jest',
      'vitejs',
      'webpack'
    ]
    const others = [
      'npm',
      'nodejs',
      'c++',
      'dart',
      'flutter',
      'python',
      'mongodb',
      'firebase',
      'git',
      'figma',
      'eslint',
      'yarn',
      'markdown',
      'github',
      'ubunto',
      'scrum',
      'cypress',
      'arduino'
    ]

    return { frontend, others }
  }
}
</script>

<style lang="scss" scoped>
.skills-header {
  display: flex;
  margin: 0 auto;
  font-size: 30px;
  font-weight: 900;
  position: relative;
  color: #12b886;
  align-items: center;
  justify-content: center;

  &::before {
    content: 'Skills';
    position: absolute;
    top: -55px;
    left: 0;
    display: inline-block;
    font-family:
      Lavishly Yours,
      cursive;
    font-size: 80px;
    line-height: 130px;
    color: #12b886;
    opacity: 0.2;
    pointer-events: none;
    left: 50%;
    transform: translate(-50%);
  }
}
.container {
  display: flex;
  margin: 0 auto;
  align-items: center;
  width: 70%;
}

.skills {
  margin: 0 auto;
  margin-bottom: 50px;
  display: flex;
  flex-direction: row;
  justify-content: center;

  &__frontend {
    &__heading {
      display: flex;
      flex-direction: row;
      flex-wrap: wrap;
      padding: 10px 0 10px 0;
      box-shadow: 0 3px 15px #16297c1a;
      margin: 40px 20px 0 20px;
      border-radius: 4px;

      & img {
        color: #12b886;
        width: 60px;
        height: 60px;
        padding: 10px;
      }

      & h2 {
        font-size: 25x;
        font-weight: 500;
        margin-top: 10px;
      }
    }

    &__list {
      display: flex;
      flex-direction: row;
      flex-wrap: wrap;
      padding: 0 10px;
      margin: 0px 20px;
      box-shadow: 0 3px 15px #16297c1a;
      border-radius: 4px;
      &--item img {
        margin: 20px 10px;
      }
    }
  }

  &__others {
    &__heading {
      display: flex;
      flex-direction: row;
      flex-wrap: wrap;
      padding: 10px 0 10px 0;
      box-shadow: 0 3px 15px #16297c1a;
      margin: 40px 20px 0 20px;
      border-radius: 4px;

      & img {
        width: 60px;
        height: 60px;
        padding: 10px;
      }

      & h2 {
        font-size: 25x;
        font-weight: 500;
        margin-top: 10px;
      }
    }

    &__list {
      display: flex;
      flex-direction: row;
      flex-wrap: wrap;
      padding: 0 10px;
      margin: 0 20px;
      box-shadow: 0 3px 15px #16297c1a;
      border-radius: 4px;
      &--item img {
        margin: 20px 10px;
      }
    }
  }
}

@media screen and (min-width: 300px) and (max-width: 900px) {
  .container {
    width: 90%;
  }
  .skills {
    flex-direction: column;
    align-items: center;
    &__frontend {
      &__list {
        &--item img {
        }
      }
    }
  }
}
</style>
