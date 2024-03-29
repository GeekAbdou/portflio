<template>
  <main>
    <Navbar />
    <Hello />
    <QuestionsList />
    <FooterBar />
  </main>
</template>

<script>
import Navbar from '@/components/Nav-bar.vue'
import Hello from '@/components/user-profile.vue'
import QuestionsList from '@/components/user-questions.vue'
import FooterBar from '@/components/footer-bar.vue'

export default {
  components: {
    Navbar,
    Hello,
    QuestionsList,
    FooterBar
  }
}
</script>
