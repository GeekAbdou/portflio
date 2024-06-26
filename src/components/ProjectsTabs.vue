<template>
  <div>
    <div class="tabs">
      <div
        v-for="tab in tabs"
        :key="tab"
        class="tabs__tab"
        :class="{ active: activeTab === tab }"
        @click="setActiveTab(tab)"
      >
        {{ tab }}
      </div>
    </div>

    <div class="tabs__projects">
      <div v-for="project in filteredProjects" :key="project.id">
        <div class="project">
          <div class="project__image-wrapper">
            <a :href="project.link" target="_blank" rel="noopener">
              <img
                class="project__image-wrapper--image"
                :src="getImg(project.image)"
                :alt="project.name"
              />
            </a>
          </div>

          <div class="project__content">
            <a class="project__name-link" :href="project.link" target="_blank" rel="noopener">{{
              project.name
            }}</a>

            <div class="project__langs">
              <div
                v-for="(lang, index) in project.langs"
                :key="`${index}`"
                class="project__langs--lang tooltip-wrapper"
              >
                <img :src="getSVG(lang)" :alt="lang" />
                <span class="tooltip-text">{{ lang }}</span>
              </div>
            </div>

            <hr />

            <p class="project__description">
              {{ project.description }}
            </p>

            <div class="project__links">
              <a
                :href="project.preview"
                class="project__link project__links__link--demo"
                target="_blank"
                rel="noopener"
                >Live Demo</a
              >
              <a
                :href="project.link"
                class="project__link project__links__link--github"
                target="_blank"
                rel="noopener"
                >Github Link</a
              >
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { ref, computed } from 'vue'

export default {
  props: {
    projects: {
      type: Array,
      required: true
    }
  },
  setup(props) {
    const tabs = ['All', 'React/NEXT', 'VUE/NUXT', 'JavaScript', 'Node/Express', 'Flutter', 'C/C++']
    const activeTab = ref('All')

    const setActiveTab = (tab) => {
      activeTab.value = tab
    }

    const filteredProjects = computed(() => {
      if (activeTab.value === 'All') {
        return props.projects
      }
      return props.projects.filter((project) => project.category === activeTab.value)
    })
    const getSVG = (item) => {
      // return import(`/src/assets/svg/${item}.svg`)
      return new URL(`/src/assets/svg/${item.toLowerCase()}.svg`, import.meta.url).href
    }
    const getImg = (item) => {
      return new URL(`/src/assets/proj/${item.toLowerCase()}`, import.meta.url).href
    }
    return { tabs, activeTab, setActiveTab, filteredProjects, getSVG, getImg }
  }
}
</script>

<style lang="scss" scoped>
.tabs {
  display: flex;
  padding-bottom: 10px;
  justify-content: center;

  &__tab {
    padding: 10px;
    border: 1px solid #ccc;
    cursor: pointer;
    margin-right: 5px;

    &.active {
      background-color: #12b886;
      color: white;
    }
  }

  &__projects {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 50px;
    max-width: 60%;
    margin: 0 auto;
  }
}

.project {
  border: 1px solid #e1e1e1;
  border-radius: 4px;
  overflow: hidden;
  background: #ffffff;
  margin: 10px;
  width: 100%;
  max-height: 650px;

  &__image-wrapper {
    max-width: 100%;
    overflow: hidden;
    width: 100%;
    object-fit: cover;
    display: block;
    transition: transform 0.5s;

    &:hover {
      transform: scale(1.2);
    }

    &--image {
      object-fit: fill;
      width: 100%;
      display: block;
    }
  }

  &__content {
    padding: 16px;
  }

  &__langs {
    display: flex;
    flex-direction: row;
    margin: 8px 0;

    &--lang {
      margin-right: 8px;
      & img {
        width: 30px;
        height: 30px;
      }
    }
  }

  & hr {
    color: #ffffff;
    border: 1px solid #f3f3f3;
    align-items: right;
  }

  &__name-link {
    background-color: transparent;
    border: 0;
    font-size: 24px;
    font-weight: 700;
    color: #12b886;
    outline: 0;
    background-image: linear-gradient(transparent 50%, rgba(18, 184, 134, 0.2) 50%);
    text-decoration: none;
    background-size: 0% 100%;
    background-repeat: no-repeat;
    will-change: background-size;
    transition: background-size 0.3s cubic-bezier(0.645, 0.645, 0.355, 1);
  }

  &__description {
    color: #666666;
    font-size: 16px;
    line-height: 1.5;
    margin-bottom: 16px;
    height: 200px;
    overflow: hidden;
  }

  &__links {
    text-align: right;
    display: flex;
    justify-content: space-between;

    &__link {
      padding: 10px 20px;
      color: #12b886;
      font-size: 16px;
      text-decoration: none;
      text-transform: uppercase;
      overflow: hidden;
      transition: 0.5s;

      &--demo {
        background: #12b886;
        color: #fff;
        border-radius: 5px;
      }

      &--github {
        background: #fff;
        color: #12b886;
        border: 1px solid #12b886;
        border-radius: 5px;
      }
    }

    & > a {
      position: relative;
      display: inline-block;
      padding: 10px 20px;
      font-size: 16px;
      text-decoration: none;
      text-transform: uppercase;
      overflow: hidden;
      transition: 0.5s;

      &:hover {
        background: #12b886;
        color: #fff;
        border-radius: 5px;
        box-shadow:
          0 0 5px #12b886cc,
          0 0 25px #12b88699,
          0 0 50px #12b88666,
          0 0 100px #12b88633;
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
      bottom: 120%;
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

@media screen and (max-width: 464px) {
  .tabs {
    &__projects {
      max-width: 90%;
    }
  }
}
</style>
