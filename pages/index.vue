<template>
  <div>
    <!-- Navigation Bar -->
    <template>
      <Navbar />
    </template>

    <!-- Content -->
    <template>
      <CardContent />
    </template>

    <!-- Footer -->
    <template>
      <Footer />
    </template>
  </div>
</template>

<script>
import Navbar from '~/components/Navbar.vue'
import CardContent from '~/components/CardContent.vue'
import Footer from '~/components/Footer.vue'

export default {
  components: {
    Navbar,
    CardContent,
    Footer,
  },
}
</script>
