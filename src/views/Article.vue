<template lang="pug">
div#about.win98popup.shadow
  header.bar
    p Blog - Article
    router-link(to='/').button.shadow
        svg(xmlns='http://www.w3.org/2000/svg' width='8px' height='7px' viewbox='0 0 8 7' fill-rule='evenodd' stroke-linejoin='round' stroke-miterlimit='2')
          path(d='M1 6V5h1V4h1V3h2v1h1v1h1v1h1v1H6V6H5V5H3v1H2v1H0V6h1zm0-4V1H0V0h2v1h1v1h2V1h1V0h2v1H7v1H6v1H2V2H1z')
  main.scroll
    section(v-html="result")
</template>
<script lang="ts">
import MarkdownIt from 'markdown-it'
let mdfile = require(`../posts/fluxcloud-serverless-hacklu-2020.md`)

const md = new MarkdownIt()
export default {
  data() {
    return {
      result: md.render(mdfile),
    }
  },
}
</script>
<style lang="scss">
#about section {
  align-items: flex-start;
  p {
    text-align: left;
  }
}
</style>
