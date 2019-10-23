<template lang="pug">
#Recommendation.page
  Card(page="Recommendation")
  .container
    .recommendation
      .kit(v-in-viewport)
        .image.image_patrick
        p.is-c4b Patrick Guilbaud, Dublin | French 
      .kit(v-in-viewport)
        .image.image_grady
        p.is-c4b O'Grady's on the Pier, Galway | Seafood
      .kit(v-in-viewport)
        .image.image_eatzen
        p.is-c4b Eatzen, Co. Meath | Asian Fusion
      .kit(v-in-viewport)
        .image.image_moran
        p.is-c4b Moran's Oyster Coattage, Galway | Seafood
      .kit(v-in-viewport)
        .image.image_pearl
        p.is-c4b Pearl Brasserie, Dublin | French
      .kit(v-in-viewport)
        .image.image_theduck
        p.is-c4b The Duck Terrace, Gorey | European
      .kit(v-in-viewport)
        .image.image_alma
        p.is-c4b Alma Cafe, Dublin | Argentinan | Brunch
      .kit(v-in-viewport)
        .image.image_grayson
        p.is-c4b The Grayson, Dublin | Wine Bar
      .kit(v-in-viewport)
        .image.image_marker
        p.is-c4b Rooftop Bar & Terrace, Dublin | Wine Bar
      .clear
</template>

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

<style lang="stylus">
@import '../assets/stylus/mixins'
.recommendation
  padding 70px 0
  > .kit
    width 33%
    float left
    padding 0 0 60px 0
    for i in 1..3
      &:nth-child(3n+{i})
        inViewport(0.2 * i)
    > .image
      margin auto
      background-size cover
      width 320px
      height 300px
      border 4px solid black
      &.image_patrick
        background-image url(/press/patrick_332x422px.jpg)
      &.image_grady
        background-image url(/press/Ogrady_332x422px.jpg)
      &.image_eatzen
        background-image url(/press/eatzen_332x422px.jpg)
      &.image_moran
        background-image url(/press/moranoyster_332x422px.jpg)
      &.image_pearl
        background-image url(/press/pearl_332x422px.jpg)
      &.image_theduck
        background-image url(/press/Duck_332x422px.jpg)
      &.image_alma
        background-image url(/press/alma_332x422px.jpg)
      &.image_grayson
        background-image url(/press/Grayson_332x422px.jpg)
      &.image_marker
        background-image url(/press/Marker_332x422px.jpg)
    > p
      text-align center

@media all and (min-width: 1px) and (max-width: 1000px)
  #Recommendation
    .recommendation
      .kit
        width 100%
        float flex

</style>
