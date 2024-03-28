<template>
  <main>
    <Navbar />
    <Hello />
    <AboutMe />
    <Myskills />
    <MyProjects />
    <FooterBar />
  </main>
</template>

<script>
import Navbar from '@/components/Nav-bar.vue'
import Hello from '@/components/user-profile.vue'
import AboutMe from '@/components/user-about.vue'
import Myskills from '@/components/user-skills.vue'
import MyProjects from '@/components/user-projects.vue'
import FooterBar from '@/components/footer-bar.vue'

export default {
  components: {
    Navbar,
    Hello,
    AboutMe,
    Myskills,
    MyProjects,
    FooterBar
  }
}
</script>
