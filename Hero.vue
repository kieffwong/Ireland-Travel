<template lang="pug">
.hero(v-on:scroll="scroll()",:class="{'hero-Home': page === 'Home', 'hero-Contact': page === 'Contact'}")
  .container
    CAddress(v-if="page === 'Home'",v-in-viewport)
    Socials(v-if="page === 'Home'",v-in-viewport)
</template>

<script>
import CAddress from '~/components/CAddress'
import Socials from '~/components/Socials'
import inViewportDirective from 'vue-in-viewport-directive'
export default {
  directives: { 'in-viewport': inViewportDirective },
  components: { CAddress, Socials },
  props: {
    page: {
      type: String,
      default: 'Home',
    }
  },
  created () {
    if (process.browser) {
      window.addEventListener('scroll', this.scroll)
    }
  },
  destroyed () {
    if (process.browser) {
      window.removeEventListener('scroll', this.scroll)
    }
  },
  methods: {
    scroll (event) {
      if (window.scrollY < window.innerHeight) {
        if (this.$store.state.menu !== 'white') {
          this.$store.commit('menuColor', 'white')
        }
      }
      if (window.scrollY > window.innerHeight) {
        if (this.$store.state.menu !== 'black') {
          this.$store.commit('menuColor', 'black')
        }
      }
    }
  },
}
</script>

<style lang="stylus">
@import '../assets/stylus/mixins'
.hero
  background-size cover
  background-position 50% 50%
  position relative
  &.hero-Home
    height 100vh
    background-image url('/banner1.jpg')
  &.hero-Contact
    height 80vh
    background-image url('/contact.jpg')
  > .container
    height 100%

  
    > .address
      inViewportFade(0.3)
    > .socials
      inViewportFade(0.4)


@media all and (min-width: 1px) and (max-width: 1000px)
  .hero
    > .container
      > .address
        display none
      > .socials
        display none

</style>
