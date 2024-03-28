<template>
  <main>
    <Navbar />
    <Hello />
    <MyProjects />
    <FooterBar />
  </main>
</template>

<script>
import Navbar from '@/components/Nav-bar.vue'
import Hello from '@/components/user-profile.vue'
import MyProjects from '@/components/user-projects.vue'
import FooterBar from '@/components/footer-bar.vue'

export default {
  components: {
    Navbar,
    Hello,
    MyProjects,
    FooterBar
  }
}
</script>
