<template>
  <div class="projects">
    <div class="projects__header" id="projects">
      <span>My Projects</span>
    </div>

    <div class="projects__tabs">
      <Tabs :projects="projects" />
    </div>
  </div>
</template>

<script>
import Tabs from './Tabs.vue'
import projectImage from '../assets/123.webp'

export default {
  components: {
    Tabs
  },
  data() {
    return {
      projects: [
        {
          name: 'Project 1',
          category: 'React',
          image: projectImage,
          link: 'https://github.com/project1',
          preview: 'https://project1.com',
          description: 'Circle is a social  mediaCircle is a social media media Circle is',
          langs: ['html', 'CSS', 'JavaScript', 'React']
        },
        {
          name: 'Project 2',
          category: 'React',
          image: projectImage,
          link: 'https://github.com/project2',
          preview: 'https://project2.com',
          description: 'Circle is a social media',
          langs: ['html', 'React']
        },
        {
          name: 'Project 3',
          category: 'Vue',
          image: projectImage,
          link: 'https://github.com/project2',
          preview: 'https://project2.com',
          description: 'Circle is a social media',
          langs: ['JavaScript', 'React']
        },
        {
          name: 'Project 4',
          category: 'Vue',
          image: projectImage,
          link: 'https://github.com/project2',
          preview: 'https://project2.com',
          description: 'Circle is a social media',
          langs: ['html', 'JavaScript', 'React']
        },
        {
          name: 'Project 5',
          category: 'Vue',
          image: projectImage,
          link: 'https://github.com/project2',
          preview: 'https://project2.com',
          description: 'Circle is a social media',
          langs: ['html', 'css', 'JavaScript', 'React']
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
.projects {
  &__header {
    display: flex;
    margin: 50px auto;
    font-size: 30px;
    font-weight: 900;
    position: relative;
    color: #12b886;
    align-items: center;
    justify-content: center;

    &::before {
      content: 'Projects';
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

    &__tabs {
      display: flex;
      justify-content: center;
    }
  }
}
</style>
