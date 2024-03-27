<template>
  <div class="projects-header">
    <span>My Projects</span>
  </div>

  <div class="container">
    <Tabs class="container__Projects" :projects="projects" />
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
          description:
            'Circle is a social mediaCircle is a social mediaCircle is a social mediaCirclCircle is a social mediaCircle is a social mediaCircle is a social mediaCircle is a social mediaCircle is a social Circle is a social mediaCircle is a social mediaCircle is a social mediaCircle is a social mediaCircle is a social mediaCircle is a social mediaCircle is a social mediaCircle is a social mediaCircle is a social mediamediaCircle is a social mediaCircle is a social mediae is a social mediaCircle is a social media',
          langs: ['HTML', 'CSS', 'JavaScript', 'React']
        },
        {
          name: 'Project 2',
          category: 'React',
          image: projectImage,
          link: 'https://github.com/project2',
          preview: 'https://project2.com',
          description: 'Circle is a social media',
          langs: ['HTML', 'React']
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
          langs: ['HTML', 'JavaScript', 'React']
        },
        {
          name: 'Project 5',
          category: 'Vue',
          image: projectImage,
          link: 'https://github.com/project2',
          preview: 'https://project2.com',
          description: 'Circle is a social media',
          langs: ['HTML', 'CSS', 'JavaScript', 'React']
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
.container {
  display: flex;
  justify-content: center;
}

.projects-header {
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
}
</style>
