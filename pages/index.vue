<template>
  <div>
    <!--  -->
    <template>
      <Navbar />
    </template>

    <!--  -->
    <template>
      <IntroCard />
    </template>

    <!--  -->
    <template>
      <Footer />
    </template>
  </div>
</template>

<script>
import Navbar from '~/components/Navbar.vue'
import IntroCard from '~/components/IntroCard.vue'
import Footer from '~/components/Footer.vue'

export default {
  components: {
    Navbar,
    IntroCard,
    Footer,
  },
}
</script>

<style lang="scss" scoped></style>
