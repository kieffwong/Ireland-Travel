<template lang="pug">
#About.page
  Card(page="About")
  .container
    .bigtitle.is-h1(v-in-viewport) Private Tour Ireland Services
    .clear
    .sections
      .section
        .thumb.thumb_airport(v-in-viewport)
        .title.is-c4b(v-in-viewport) Pick-up Service
        p(v-in-viewport) Pick-up from airport and settle down in accomodation
      .section
        .thumb.thumb_dinning(v-in-viewport)
        .title.is-c4b(v-in-viewport) Dining Experience
        p(v-in-viewport) Bring our guest to the top quality restaurant
      .section
        .thumb.thumb_personal(v-in-viewport)
        .title.is-c4b(v-in-viewport) Personal Assistant
        p(v-in-viewport) We will help you as a personal assistant from taking photos, video and arrange anything you need to satisfy our customers.
      .section
        .thumb.thumb_gadgets(v-in-viewport)
        .title.is-c4b(v-in-viewport) Gadgets
        p(v-in-viewport) We will offer you our latest gadgets, e.g. electric scooters, Gopro, selfie sticks and Drone.
      .clear
    .bigtitle.is-h1(v-in-viewport) Mission
    .clear
    .principal
      .image(v-in-viewport)
        .inner
      .copy(v-in-viewport)
        .inner We love to meet new people, we would love to share our expertise to ensure you will have a fantastic experience during your journey!
      .clear

</template>

<style lang="stylus">
@import '../assets/stylus/mixins'

#About.page
  > .container
    padding 120px 0
    .bigtitle
      inViewport(0)
      float left
      clear both
      padding 0 0 20px 0
      margin 0 0 20px 0
      border-bottom 5px solid black
    .sections
      padding 20px 0px 20px 20px
      margin-bottom 80px
      > .section
        width 50%
        margin-bottom 40px
        float left
        &:nth-child(1)
          > .thumb
            inViewport(0.1)
          > .title
            inViewport(0.2)
          > p
            inViewport(0.3)
        &:nth-child(2)
          > .thumb
            inViewport(0.1)
          > .title
            inViewport(0.2)
          > p
            inViewport(0.3)
        &:nth-child(3)
          > .thumb
            inViewport(0.1)
          > .title
            inViewport(0.2)
          > p
            inViewport(0.3)
        &:nth-child(4)
          > .thumb
            inViewport(0.1)
          > .title
            inViewport(0.2)
          > p
            inViewport(0.3)
        > .thumb
          width 338px
          height 338px
          margin-bottom 30px
          background-size cover
          &.thumb_airport
            background-image url(/about/airport_338x338px.jpg)
          &.thumb_dinning
            background-image url(/about/Dinning_338x338px.jpg)
          &.thumb_personal
            background-image url(/about/personal.jpg)
          &.thumb_gadgets
            background-image url(/about/gadgets_338x338px.jpg)
           > .title
            margin-top 30px
            padding 30px 30px 10px 20px
           >  p
              margin-right 60px
    .principal
      .image
        inViewport(0.1)
        width 50%
        float left
        .inner
          width 460px
          height 600px
          background-image url(/about/deer_460x600.jpg)
          background-size cover
      .copy
        inViewport(0.2)
        width 50%
        float left
        > .inner
          margin-top 90px
          margin-right 90px

@media all and (min-width: 1px) and (max-width: 1000px)
  #About.page
    padding 90px 0
    .container
      .bigtitle
        font-size 30px
        text-align center
        float none
        margin 20px
      > .sections
        > .section
          width 100%
          margin 40px 0
          float none
          > .thumb
            margin auto
          > .title
            text-align center
          > p
            margin 20px

      > .principal
        padding 20px
        > .image
          width 100%
          float none
          > .inner
            width 100%
        > .copy
          width 100%
          float none
          > .inner
            margin 30px 0 

</style>

<script>
import Card from '~/components/Card.vue'
import inViewportDirective from 'vue-in-viewport-directive'
export default {
  components: { Card },
  directives: { 'in-viewport': inViewportDirective },
  created () {
    this.$store.commit('menuColor', 'black')
  },
}
</script>
