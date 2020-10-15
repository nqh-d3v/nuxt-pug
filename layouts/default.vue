<template lang="pug">
  div
    - var languages = [{cont: 'EN', val: 'en', selected: true}, {cont: 'VI', val: 'vi'}];
    //- Navbar fixed on top
    nav.navbar.is-fixed-top.has-shadow.is-white(
      role='navigation'
      aria-label='main navigation'
    )
      .navbar-brand
        a.navbar-item(href='/')
          img(
            src='https://dev.legalclarus.com/_nuxt/img/images-legal-clarus-logo@2x.148bb0a.png'
            height='80'
          )

        a.navbar-burger.burger(
          role='button'
          aria-label='menu'
          aria-expanded=false
          data-target='navbarBasicExample'
        )
          span(aria-hidden=true)/
          span(aria-hidden=true)/
          span(aria-hidden=true)/

      #navbarBasicExample.navbar-menu
        .navbar-start
          a.navbar-item
            b-icon(icon="home" type="is-primary")
            | Home

          .navbar-item.has-dropdown.is-hoverable
            a.navbar-link Find a Lawyer

            .navbar-dropdown
              a.navbar-item Some things here
              a.navbar-item Some things here
          .navbar-item.has-dropdown.is-hoverable
            a.navbar-link Services

            .navbar-dropdown
              a.navbar-item Some things here
              a.navbar-item Some things here
          
          a.navbar-item Knowledge
          a.navbar-item About us

        .navbar-end
          .navbar-item
            .field.has-addons
              .control
                input.input(type='text' placeholder='Name practice areas')
              div.control
                a.button
                  b-icon(
                    icon='magnify'
                    type='is-primary'
                  )/

          .navbar-item
            a.button.btn--login Login
          .navbar-item
            .select
              select
                each lan in languages
                  option(
                    value=lan.val
                    selected= (lan.selected) ? true : false
                  )= lan.cont
    
    Nuxt.pt-100/
</template>

<script>

  export default {
    data () {
      return {
        languages: [
          {cont: 'EN', val: 'en', selected: true},
          {cont: 'VI', val: 'vi'},
        ],
      };
    },
  };
</script>

<style lang="sass">
.pt-100
  padding-top: 100px
.pt--1-5rem
  padding-top: 1.5px
html
  font-family: 'Source Sans Pro', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif
  font-size: 16px
  word-spacing: 1px
  -ms-text-size-adjust: 100%
  -webkit-text-size-adjust: 100%
  -moz-osx-font-smoothing: grayscale
  -webkit-font-smoothing: antialiased
  box-sizing: border-box
nav
  height: 100px
  img
    max-height: 90px !important
.is-active
  color: #002366 !important
  background-color: white !important
  font-weight: 600 !important
.btn--login
  background-color: #002366
  color: white !important
  transition: .5s
  &:hover
    background-color: #003aa7
*,
*::before,
*::after
  box-sizing: border-box
  margin: 0

</style>
