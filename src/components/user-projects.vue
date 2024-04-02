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
import Tabs from './ProjectsTabs.vue'

export default {
  components: {
    Tabs
  },
  data() {
    return {
      projects: [
        {
          id: 1,
          name: 'DevDisc',
          category: 'React',
          image: 'devdisc.jpeg',
          link: 'https://github.com/GeekAbdou/DevDisc',
          preview: 'https://dev-disc.vercel.app/',
          description: 'Developers Discussion Fourm',
          langs: ['html', 'CSS', 'JavaScript', 'React']
        },
        {
          id: 2,
          name: 'Leon',
          category: 'React',
          image: 'leon.jpeg',
          link: 'https://github.com/GeekAbdou/FrontEnd_Practice/tree/main/Template_one',
          preview: 'https://geekabdou.github.io/FrontEnd_Practice/Template_one/',
          description: 'We are Leon - Super Creative & Minimal Agency Web Template',
          langs: ['html', 'CSS', 'JavaScript', 'React']
        },
        {
          id: 3,
          name: 'Beautiful Escape',
          category: 'React',
          image: 'surf.jpeg',
          link: 'https://github.com/GeekAbdou/FrontEnd_Practice/tree/main/Template_Three',
          preview: 'https://geekabdou.github.io/FrontEnd_Practice/Template_Three/index.html#',
          description:
            'One of the greatest things about the sport of surfing is that you need only three things: your body, a surfboard, and a wave. ',
          langs: ['html', 'CSS', 'JavaScript', 'React']
        },
        {
          id: 4,
          name: 'Kasper',
          category: 'React',
          image: 'kasper.jpeg',
          link: 'https://github.com/GeekAbdou/FrontEnd_Practice/tree/main/Template_two',
          preview: 'https://geekabdou.github.io/FrontEnd_Practice/Template_two/',
          description: 'We are Leon - Super Creative & Minimal Agency Web Template',
          langs: ['html', 'CSS', 'JavaScript', 'React']
        },
        {
          id: 5,
          name: 'Infinity',
          category: 'React',
          image: 'surf.jpeg',
          link: 'https://github.com/GeekAbdou/VueCLI/tree/main',
          preview: 'https://github.com/GeekAbdou/VueCLI/tree/main',
          description:
            ' This is an example of decribtion of bla on bla This is an example of decribtion of bla on blaThis is an example of decribtion of bla on bla  ',
          langs: ['html', 'CSS', 'JavaScript', 'React']
        },
        {
          id: 6,
          name: 'Image processing API',
          category: 'React',
          image: 'imgprocessing.jpeg',
          link: 'https://github.com/GeekAbdou/Img-Processing-API',
          preview: 'https://github.com/GeekAbdou/Img-Processing-API',
          description:
            'it resize images to new width and height.if the image is already resized it will not resize it again and will fetch the existing thumbnail',
          langs: ['html', 'CSS', 'JavaScript', 'React']
        },
        {
          id: 7,
          name: 'Music Player',
          category: 'React',
          image: 'musicplayer.jpeg',
          link: 'https://github.com/GeekAbdou/Vanilla_JS_Apps/tree/main/Music%20Player/',
          preview: 'https://geekabdou.github.io/Vanilla_JS_Apps/Music%20Player/',
          description: 'Basic Function of Msuic Player, Repeate or shuffle next music',
          langs: ['html', 'CSS', 'JavaScript', 'React']
        },
        {
          id: 8,
          name: 'Analog Clock',
          category: 'React',
          image: 'clock.jpeg',
          link: 'https://github.com/GeekAbdou/Vanilla_JS_Apps/tree/main/Analog%20Clock',
          preview: 'https://geekabdou.github.io/Vanilla_JS_Apps/Analog%20Clock/',
          description: 'Analog Clock',
          langs: ['html', 'CSS', 'JavaScript', 'React']
        },
        {
          id: 9,
          name: 'JS Todo App',
          category: 'React',
          image: 'jstodo.jpeg',
          link: 'https://github.com/GeekAbdou/Vanilla_JS_Apps/tree/main/TODO%20App',
          preview: 'https://geekabdou.github.io/Vanilla_JS_Apps/TODO%20App/',
          description: 'Analog Clock',
          langs: ['html', 'CSS', 'JavaScript', 'React']
        },
        {
          id: 10,
          name: 'Admin Panel',
          category: 'React',
          image: 'adminpanel.jpeg',
          link: 'https://github.com/GeekAbdou/AdminPanel?tab=readme-ov-file',
          preview: 'https://geekabdou.github.io/AdminPanelPage/#/',
          description: 'Admin Panel',
          langs: ['html', 'CSS', 'JavaScript', 'React']
        },
        {
          id: 9,
          name: 'Spark Cart',
          category: 'React',
          image: 'cartspark.jpeg',
          link: 'https://github.com/GeekAbdou/CartSpark',
          preview: 'https://github.com/GeekAbdou/CartSpark',
          description: 'Analog Clock',
          langs: ['html', 'CSS', 'JavaScript', 'React']
        },
        {
          id: 9,
          name: 'Ishop App',
          category: 'React',
          image: 'ishop.jpeg',
          link: 'https://github.com/GeekAbdou/iShop',
          preview: 'https://github.com/GeekAbdou/iShop',
          description: 'Analog Clock',
          langs: ['html', 'CSS', 'JavaScript', 'React']
        },
        {
          id: 9,
          name: ' AVR_GPIO_Driver',
          category: 'React',
          image: 'gpio.jpeg',
          link: 'https://github.com/GeekAbdou/AVR_GPIO_Driver',
          preview: 'https://github.com/GeekAbdou/AVR_GPIO_Driver',
          description: 'Analog Clock',
          langs: ['html', 'CSS', 'JavaScript', 'React']
        },
        {
          id: 9,
          name: 'InstaLog',
          category: 'React',
          image: 'instaLog.jpeg',
          link: 'https://github.com/GeekAbdou/InstaLog',
          preview: 'instalog-ebon.vercel.app/',
          description: 'InstaLog - Instabug FrontEnd Internship Challenge',
          langs: ['html', 'CSS', 'JavaScript', 'React']
        },
        {
          id: 9,
          name: 'Adopt Me',
          category: 'React',
          image: 'adoptme.jpeg',
          link: 'https://github.com/GeekAbdou/InstaLog',
          preview: 'https://adopt-me-azure.vercel.app/',
          description: 'InstaLog - Instabug FrontEnd Internship Challenge',
          langs: ['html', 'CSS', 'JavaScript', 'React']
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
