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
  </div>
</template>

<script>
import Navbar from '~/components/Navbar.vue'
import IntroCard from '~/components/IntroCard.vue'
export default {
  components: {
    Navbar,
    IntroCard
  },
}
</script>

<style lang="scss" scoped></style>
