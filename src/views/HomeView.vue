<template>
  <main>
    <Navbar />
    <Hello />
  </main>
</template>

<script>
import Navbar from '@/components/Nav-bar.vue'
import Hello from '@/components/hello-section.vue'

export default {
  components: {
    Navbar,
    Hello
  }
}
</script>
