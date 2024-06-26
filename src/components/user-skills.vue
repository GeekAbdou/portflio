<template>
  <div class="skl" id="skills">
    <div class="skills-header">
      <span>My Skills</span>
    </div>

    <div class="container">
      <div class="skills">
        <div class="skills__frontend">
          <div class="skills__frontend__heading">
            <img :src="frontendSVG" alt="Frontend" />
            <h2>&lt;Frontend/&gt;</h2>
          </div>

          <div class="skills__frontend__list">
            <div
              v-for="(item, index) in frontend"
              :key="`frontend-${index}`"
              class="skills__frontend__list--item tooltip-wrapper"
            >
              <img :src="getSVG(item)" :alt="item" />

              <span class="tooltip-text">{{ item }}</span>
            </div>
          </div>
        </div>

        <div class="skills__others">
          <div class="skills__others__heading">
            <img :src="othersSVG" alt="Others" />
            <h2>Others</h2>
          </div>

          <div class="skills__others__list">
            <div
              v-for="(item, index) in others"
              :key="`others-${index}`"
              class="skills__others__list--item tooltip-wrapper"
            >
              <img :src="getSVG(item)" :alt="item" />
              <span class="tooltip-text">{{ item }}</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import frontendSVG from '/src/assets/svg/frontend.svg'
import othersSVG from '/src/assets/svg/others.svg'
const frontend = [
  'html',
  'css',
  'javascript',
  'typescript',
  'react',
  'redux',
  'nextjs',
  'vuejs',
  'nuxtjs',
  'vuex',
  'bootstrap',
  'sass',
  'tailwind',
  'materialui',
  'jasmine',
  'jest',
  'vitejs',
  'webpack'
]
const others = [
  'npm',
  'nodejs',
  'cplusplus',
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
  'ubuntu',
  'scrum',
  'cypress',
  'arduino'
]

const getSVG = (item) => {
  // return import(`/src/assets/svg/${item}.svg`)
  return new URL(`/src/assets/svg/${item.toLowerCase()}.svg`, import.meta.url).href
}
</script>

<style lang="scss" scoped>
.skl {
  display: flex;
  flex-direction: column;
  justify-content: center;
  height: 100vh;
  @media screen and (max-width: 860px) {
    height: auto;
  }
}

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

  &__frontend,
  &__others {
    &__heading {
      display: flex;
      flex-direction: row;
      flex-wrap: wrap;
      padding: 10px 0;
      box-shadow: 0 3px 15px #16297c1a;
      margin: 40px 20px 0;
      border-radius: 4px;

      img {
        color: #12b886;
        width: 60px;
        height: 60px;
        padding: 10px;
      }

      h2 {
        font-size: 25px;
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

      &--item {
        position: relative;
        display: inline-block;
        img {
          margin: 20px 10px;
        }

        img:hover::after {
          content: attr(title);
          position: absolute;
          bottom: 100%;
          left: 50%;
          transform: translateX(-50%);
          padding: 5px;
          background-color: rgba(0, 0, 0, 0.7);
          color: #fff;
          font-size: 14px;
          border-radius: 4px;
          white-space: nowrap;
          z-index: 999;
          visibility: hidden;
          opacity: 0;
          transition:
            visibility 0s linear 0.3s,
            opacity 0.3s linear;
        }

        img:hover::after {
          visibility: visible;
          opacity: 1;
          transition-delay: 0s;
        }
      }
    }
  }

  .tooltip-wrapper {
    position: relative;
    display: inline-block;

    .tooltip-text {
      visibility: hidden;
      opacity: 0;
      position: absolute;
      bottom: 90%;
      left: 50%;
      transform: translateX(-50%);
      padding: 5px;
      background-color: rgba(0, 0, 0, 0.9);
      color: #fff;
      font-size: 14px;
      border-radius: 4px;
      white-space: nowrap;
      z-index: 999;
      transition:
        opacity 0.3s,
        visibility 0.3s;

      &::first-letter {
        text-transform: capitalize;
      }

      &::before {
        content: '';
        position: absolute;
        top: 100%;
        left: 50%;
        margin-left: -5px;
        border-width: 5px;
        border-style: solid;
        border-color: rgba(0, 0, 0, 0.9) transparent transparent transparent;
      }
    }

    &:hover .tooltip-text {
      visibility: visible;
      opacity: 1;
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

    &__frontend,
    &__others {
      &__list {
        &--item img {
          // Responsive styles if needed
        }
      }
    }
  }
}
</style>
