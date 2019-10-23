<template lang="pug">
#Bottom.is-c1sb
  .container
    .footer
      .copy.is-c1sb &copy; Kieff Desgin Studio
      .copy.is-c1sb
        | SITE BY 
        a(href="https://kieffwong.github.io/Portfolio/",target="_new") Kieff Wong
      

    .baddress
      .copy Private Tour Ireland
      a.copy(href="https://goo.gl/maps/nFZzMHGLrUZMQxXy9",target="_new") Dublin
      a.copy(href="https://goo.gl/maps/nFZzMHGLrUZMQxXy9",target="_new") Ireland
      a.copy(href="https://goo.gl/maps/nFZzMHGLrUZMQxXy9",target="_new") D15 XW56
    .bsocials
        a.social.social_facebook facebook
        .separator
        a.social.social_instagram instagram
    .clear
</template>

<style lang="stylus">
json('../assets/colors.json')
#Bottom
  padding 60px
  text-transform uppercase
  letter-spacing 2px
  > .container
    > .footer
      float right   
      > .copy
        padding 4px 0
        color black
        text-decoration none
        > a
          color black
          text-decoration none
          transition all 0.2s ease
          &:hover
            color rgba(black, 0.5)
            text-decoration underline

@media all and (min-width: 1px) and (max-width: 1000px)
  #Bottom
    padding 20px 10px
    > .container
      text-align center
      > .footer
        float right

</style>
