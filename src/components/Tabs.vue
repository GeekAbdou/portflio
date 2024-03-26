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
      <div class="" v-for="project in filteredProjects" :key="project.name">
        <div class="project">
          <div class="project__image-wrapper">
            <img class="project__image-wrapper--image" :src="project.image" :alt="project.name" />
          </div>
          <div class="project__content">
            <a class="project__name-link" :href="project.link" target="_blank" rel="noopener">{{
              project.name
            }}</a>
            <p class="project__description">
              {{ project.description }}
            </p>
            <div class="project__links">
              <a
                :href="project.link"
                class="project__link project__link--demo"
                target="_blank"
                rel="noopener"
                >Live Demo</a
              >
              <a
                :href="project.preview"
                class="project__link project__link--github"
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
    const tabs = ['All', 'React', 'Vue', 'Node', 'Flutter']
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

    return { tabs, activeTab, setActiveTab, filteredProjects }
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
    width: 1200px;
  }
}

.project {
  border: 1px solid #e1e1e1;
  border-radius: 4px;
  overflow: hidden;
  background: #ffffff;
  margin: 10px;
  width: 400px;
  height: 500px;

  &__image-wrapper {
    max-width: 100%;
    overflow: hidden;
    width: 200px;
    height: 200px;
    object-fit: cover;
    width: 100%;
    display: block;

    &--image {
      object-fit: cover;
      width: 100%;
      display: block;
    }
  }

  &__content {
    padding: 16px;
  }

  &__name-link {
    color: #333333;
    font-weight: bold;
    text-decoration: none;
    font-size: 20px;
    display: block;
    margin-bottom: 8px;
  }

  &__description {
    color: #666666;
    font-size: 16px;
    line-height: 1.5;
    margin-bottom: 16px;
  }

  &__links {
    text-align: right;
    display: flex;
    justify-content: space-between;

    & > a {
      position: relative;
      display: inline-block;
      padding: 10px 20px;
      color: #12b886;
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
}
</style>
