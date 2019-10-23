<template lang="pug">
.card.is-bg-iceberg
  .container
    .title.is-froly(v-in-viewport,v-if="page === 'Home'") Tailor Made Tour
    .title.is-froly.title-contact(v-in-viewport,v-if="page === 'Contact'") Contact
    .title.is-froly.title-recommendation(v-in-viewport,v-if="page === 'Recommendation'") Restaurants
    .title.is-froly.title-about(v-in-viewport,v-if="page === 'About'") About
    .title.is-froly.title-about(v-in-viewport,v-if="page === 'Jobs'") careers

    .quote(v-in-viewport,v-if="page === 'About'")
      p Excellent since the pick up service and the tour arrangment, the best was being our top photographer and filmer, familiar with all the popular photo spots.
      i — John Tan
    .quote(v-in-viewport,v-if="page === 'Recommendation'")
      p The recommended restaurants are lovely and very nice environment!
      i - Michael Taylor
    .quote(v-in-viewport,v-if="page === 'Jobs'")
      p We love to meet new people and work with people, we proud of what we are doing!
      
    .columns
      .column(v-in-viewport,v-if="page === 'Contact'")
        .block
          .title.is-c4b GIVE US A CALL
          a(href="tel: +353834608953") +353834608953

      .column(v-in-viewport,v-if="page === 'Contact'")
        .block
          .title.is-c4b DROP US A LINE
          a(href="mailto:campoinvest@gmail.com") E-mail
          a(href="mailto:campoinvest@gmail.com") Media Inquries

      .column(v-in-viewport,v-if="page === 'Contact'")
        .block
          .title.is-c4b TRAVEL WITH US
          a(href="mailto:campoinvest@gmail.com",target="_new") Join our tour
          a(href="mailto:campoinvest@gmail.com",target="_new") Tailor made tour avaliable

    .copy.is-c4(v-in-viewport,v-if="page === 'Home'") Private Tour specializes in high-end touring, we design your journey from pick up in airport, get a nice coffee in morning and create vlog or engagment proposal.

    .clear
</template>

<style lang="stylus">
@import '../assets/stylus/mixins'
.card
  background-color iceberg
  padding 120px 30px
  > .container

    > .title
      inViewportFade(0)
      text-align right
      display inline-block
      transform rotate(0deg)
      margin-top 30px
      letter-spacing 5px
      &.title-contact
        margin-top 30px
      &.title-recommendation
        margin-top 30px
      &.title-about
        margin-top 30px

    > .columns
      margin-top -50px
      display flex
      justify-content center
      flex-direction row
      align-content center
      margin-left 200px
      > .column
        flex-grow 1
        inViewport(0.1)
        .block
          > .title
            padding 0 0 10px 0
          margin-bottom 10px
        a
          display block
          text-decoration none
          color black
          margin 5px 0

    .quote
      inViewport(0.1)
      margin -70px auto 0 auto
      width 640px

    > .copy
      inViewport(0.1)
      width 600px
      float right
      line-height 30px
      margin-right 30px
      margin-top -40px

    .est
      inViewport(0.2)
      float right
      > .year
        padding 0 0 10px 0
        text-align center
        letter-spacing 13px
      > .copy
        text-transform uppercase
        letter-spacing 4px

@media all and (min-width: 1px) and (max-width: 1000px)
  .card
    padding 30px 20px
    > .container
      > .title
        transform rotate(0deg)
        margin-top 30px
        margin-bottom 30px
        text-align center
        display block
      > .copy
        width auto
        margin-right 0
        margin-top 30px
      > .quote
        width auto
        margin 30px auto

      > .columns
        display block
        margin-top 20px
        margin-left 0px
        > .column
          float none
          width auto
          text-align center
          margin 0 0 30px 0
</style>

<script>
import form from '~/components/Form'
import inViewportDirective from 'vue-in-viewport-directive'
export default {
  directives: { 'in-viewport': inViewportDirective },
  props: {
    page: {
      type: String,
      default: 'Home',
    }
  }
}
</script>
