<template lang="pug">
  //- Mixin card icon
  mixin cardImg(imgUrl, imgDesc)
    .card.cardImg.is-shadowless.column.is-1.p-0.is--1d8
      .card-image
        figure.image.is-64x64.m-auto
          img(src=imgUrl alt='Placeholder image')
      .card-content
        .content= imgDesc
  //- Mixin card title
  mixin sectionTitle(id, title, cardImgs)
    .section.section-view(id=id)
      h4.section-title.mb-2= title
      div
        .columns.is-mobile.m-0
          each card in cardImgs
            +cardImg(card.imgUrl, card.imgDesc)
  
  // Main content here
  section.main-content.columns
    aside.section.has-background-white.column.is-2.pt-5
      ul.menu-list
        a(v-for="item of items" v-bind:class="item.class")
          li {{item.title}}

    .column.is-10
      div
        //- Define here
        - 
          var sectionTitles = [ 
            {
              id: 'popular_practice_areas',
              title: 'Popualar Practice Areas',
              cardImgs: [ {imgUrl: 'https://dev.legalclarus.com/_nuxt/img/divorce-family.8fe8372.png', imgDesc: 'Divorce abc abc abc acb abc'}, {imgUrl: 'https://dev.legalclarus.com/_nuxt/img/divorce-family.8fe8372.png', imgDesc: 'Contract / Business'}, {imgUrl: 'https://dev.legalclarus.com/_nuxt/img/divorce-family.8fe8372.png', imgDesc: 'Real Estate'}, {imgUrl: 'https://dev.legalclarus.com/_nuxt/img/divorce-family.8fe8372.png', imgDesc: 'Personal Injury'}, {imgUrl: 'https://dev.legalclarus.com/_nuxt/img/divorce-family.8fe8372.png', imgDesc: 'Litigation & Disputes'}, {imgUrl: 'https://dev.legalclarus.com/_nuxt/img/divorce-family.8fe8372.png', imgDesc: 'Debte Recovery'}, {imgUrl: 'https://dev.legalclarus.com/_nuxt/img/divorce-family.8fe8372.png', imgDesc: 'Civil Celebrant Service'}, {imgUrl: 'https://dev.legalclarus.com/_nuxt/img/divorce-family.8fe8372.png', imgDesc: 'Criminal Defense'} ]
            },
            {
              id: 'business',
              title: 'Business',
              cardImgs: [ {imgUrl: 'https://dev.legalclarus.com/_nuxt/img/divorce-family.8fe8372.png', imgDesc: 'Banking'}, {imgUrl: 'https://dev.legalclarus.com/_nuxt/img/divorce-family.8fe8372.png', imgDesc: 'Contract / Business'}, {imgUrl: 'https://dev.legalclarus.com/_nuxt/img/divorce-family.8fe8372.png', imgDesc: 'Corporate & Commercial'}, {imgUrl: 'https://dev.legalclarus.com/_nuxt/img/divorce-family.8fe8372.png', imgDesc: 'Corporate & Finance'}, {imgUrl: 'https://dev.legalclarus.com/_nuxt/img/divorce-family.8fe8372.png', imgDesc: 'Funds'}, {imgUrl: 'https://dev.legalclarus.com/_nuxt/img/divorce-family.8fe8372.png', imgDesc: 'Intellectual Property'}, {imgUrl: 'https://dev.legalclarus.com/_nuxt/img/divorce-family.8fe8372.png', imgDesc: 'Startup Legal Services'} ]
            },
            {
              id: 'criminal',
              title: 'Criminal',
              cardImgs: [ {imgUrl: 'https://dev.legalclarus.com/_nuxt/img/divorce-family.8fe8372.png', imgDesc: 'Criminal'} ]
            },
          ];
        //- Content here
        each sectionTitle in sectionTitles
          +sectionTitle(sectionTitle.id, sectionTitle.title, sectionTitle.cardImgs)
</template>

<script>
export default {
  name: 'home-page',
  data () {
    return {
      items: [
        { title: 'Popular Practive Areas', class: 'is-active', to: { name: 'popular_practice_areas' } },
        { title: 'Business', to: { name: 'business' } },
        { title: 'Criminal', to: { name: 'criminal' } },
        { title: 'Civil Claim', to: { name: 'civil_claim' } },
        { title: 'Family', to: { name: 'family' } },
        { title: 'Personal Injury', to: { name: 'personal_injury' } },
        { title: 'Real Estate', to: { name: 'real_estate' } },
        { title: 'Wilis and Probate', to: { name: 'wilis_and_probate' } },
        { title: 'Other', to: { name: 'other' } },
      ],
    };
  },
};
</script>

<style lang="sass">
.container
  margin: 0 auto
  min-height: 100vh
  display: flex
  justify-content: center
  align-items: center
  text-align: center

.title
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif
  display: block
  font-weight: 300
  font-size: 100px
  color: #35495e
  letter-spacing: 1px


.subtitle
  font-weight: 300
  font-size: 42px
  color: #526488
  word-spacing: 5px
  padding-bottom: 15px

.is--1d8
  width: calc(100% / 8) !important
.m-auto
  margin: auto !important

.section-view
  width: 100%
  min-height: 200px
.section-view h4.section-title
  font-size: 20px
  color: #002365
  font-weight: 600
  border-bottom: 1px solid #e2e2e2
.section-view .columns
  align-items: stretch
.cardImg .card-content
  padding: 5px
.cardImg .card-content .content
  font-size: 12px
  text-align: center
</style>
