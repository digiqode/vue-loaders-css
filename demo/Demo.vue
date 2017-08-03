<template lang="pug">
  div#dq-page
    div.dq-container
      div.dq-row
        div.dq-col
          h1 Vue Loaders CSS Demo
          p Vue wrapper for Loaders.css, the delightful and performance-focused pure css loading animations
      div.dq-row
        div.dq-col
          div.dq-demo-mode-buttons
            button(type='button', v-bind:class='{"button-link": mode === "showAllLoaders"}', v-on:click='changeMode("selectedAnimationLoader")').button Selected Animation Loader
            button(type='button', v-bind:class='{"button-link": mode === "selectedAnimationLoader"}', v-on:click='changeMode("showAllLoaders")').button Show All Loaders
            a(href='https://github.com/digiqode/vue-loaders-css').button.button-link View on Github
      div.dq-demo-showcase-container
        transition(name='fade')
          div(v-if='mode === "selectedAnimationLoader"').dq-row.dq-demo-selected-showcase
            div.dq-col.dq-col-7-12
              h5 Usage
              pre.dq-code-template
                = `<template>\n  <vue-loaders-css type="{{ selectedOption }}"></vue-loaders-css>\n</template>`
              pre.dq-code-script
                = `<script>\n  import VueLoadersCss from 'vue-loaders-css'\n  export default {\n    components: {\n      VueLoadersCss\n    }\n  }\n</script>`
              pre.dq-code-style
                = `<style>\n  $primary-color: #FF6347;\n  @import "~loaders.css/src/animations/{{ selectedOption }}.scss";\n</style>`
            div.dq-col.dq-col-5-12
              h5 Animation Type
              select(v-model='selectedOption')
                option(v-for='option in options', v-bind:value='option.value') {{ option.value }}
              vue-loaders-css(v-bind:type='selectedOption')
        transition(name='fade')
          div(v-if='mode === "showAllLoaders"').dq-row.dq-demo-showall-showcase
            div(v-for="option in options").dq-col.dq-col-3-12
              vue-loaders-css(v-bind:type="option.value")
              p.text-center {{ option.value }}
      div.dq-row
        div.dq-col
          - var love = '<a href="https://www.digiqode.com/"> ❤ </a>'
          div.text-small Made with !{love} by #[a(href='https://www.digiqode.com/') DigiQode].
          div.text-small Powered by #[a(href='https://vuejs.org/') Vue], #[a(href='https://connoratherton.com/loaders') Loaders.css], and #[a(href='https://shoelace.style/') Shoelace Style].
          div.text-small Hosted by #[a(href='http://www.vultr.com/?ref=7169312') Vultr].
</template>

<script>
  import VueLoadersCss from '../src/VueLoadersCss.vue'

  export default {
    name: 'VueLoadersCssDemo',
    components: {
      VueLoadersCss
    },
    data () {
      return {
        mode: 'selectedAnimationLoader',
        selectedOption: 'line-scale-pulse-out',
        options: [
          { value: 'ball-pulse' },
          { value: 'ball-grid-pulse' },
          { value: 'ball-clip-rotate' },
          { value: 'ball-clip-rotate-pulse' },
          { value: 'square-spin' },
          { value: 'ball-clip-rotate-multiple' },
          { value: 'ball-pulse-rise' },
          { value: 'ball-rotate' },
          { value: 'cube-transition' },
          { value: 'ball-zig-zag' },
          { value: 'ball-zig-zag-deflect' },
          { value: 'ball-triangle-path' },
          { value: 'ball-scale' },
          { value: 'line-scale' },
          { value: 'line-scale-party' },
          { value: 'ball-scale-multiple' },
          { value: 'ball-pulse-sync' },
          { value: 'ball-beat' },
          { value: 'line-scale-pulse-out' },
          { value: 'line-scale-pulse-out-rapid' },
          { value: 'ball-scale-ripple' },
          { value: 'ball-scale-ripple-multiple' },
          { value: 'ball-spin-fade-loader' },
          { value: 'line-spin-fade-loader' },
          { value: 'triangle-skew-spin' },
          { value: 'pacman' },
          { value: 'ball-grid-beat' },
          { value: 'semi-circle-spin' }
        ]
      }
    },
    methods: {
      changeMode(selectedMode) {
        this.mode = selectedMode
      }
    }
  }
</script>

<style lang="scss">
@import "~shoelace-css/dist/shoelace.css";
@import url("https://fonts.googleapis.com/css?family=Zilla+Slab:300,400");
:root {
  --font-sans-serif: sans-serif;
  --font-serif: serif;
  --font-system: 'Zilla Slab', serif;
  --font-monospace: monospace;
  --body-color: lighten(#192231, 50%);
  --headings-color: #FFFFFF;
  --pre-color: lighten(#192231, 50%);
  --pre-bg-color: lighten(#192231, 10%);
  --link-text-decoration-hover: none;
}

$primary-color: #FF6347;
@import "~loaders.css/src/loaders.scss";

$background-color: #192231;
body {
  overflow-y: scroll;
}
#dq-page {
  color: var(--body-color);
  background: $background-color;
  min-height: 100vh;
  height: 100%;
}
.dq-container {
  margin: 0 auto;
  padding: 2rem 0;
  max-width: 1280px;
}
.dq-row {
  display: flex;
  flex-wrap: wrap;
  min-width: 100%;
}
.dq-col {
  width: 100%;
  padding: 0.5rem;
  &.dq-col-1-12 {
    width: 8.33333%;
  }
  &.dq-col-2-12 {
    width: 16.66667%;
  }
  &.dq-col-3-12 {
    width: 25%;
  }
  &.dq-col-4-12 {
    width: 33.33333%;
  }
  &.dq-col-5-12 {
    width: 41.66667%;
  }
  &.dq-col-6-12 {
    width: 50%;
  }
  &.dq-col-7-12 {
    width: 58.33333%;
  }
  &.dq-col-8-12 {
    width: 66.66667%;
  }
  &.dq-col-9-12 {
    width: 75%;
  }
  &.dq-col-10-12 {
    width: 83.33333%;
  }
  &.dq-col-11-12 {
    width: 91.66667%;
  }
  &.dq-col-12-12 {
    width: 100%;
  }
}
.dq-demo-mode-buttons {
  margin-bottom: 15px;
  .button {
    margin-right: 15px;
  }
}
.vue-loaders-css-container {
  background: lighten($background-color, 5%);
  border-radius: 5px;
  display: flex;
  align-items: center;
  justify-content: center;
  .dq-demo-selected-showcase & {
    height: 418px;
    margin-top: 9px;
  }
  .dq-demo-showall-showcase & {
    height: 150px;
    margin-bottom: 10px;
  }
}
.dq-demo-showcase-container {
  position: relative;
}
.dq-demo-selected-showcase {
  .dq-col {
    @media only screen and (max-width: 960px) {
      width: 100%;
    }
  }
}
.dq-demo-showall-showcase {
  .dq-col {
    @media only screen and (max-width: 720px) {
      width: 50%;
    }
    @media only screen and (max-width: 480px) {
      width: 100%;
    }
  }
}
pre {
  font-size: 15px;
}
.button {
  &:focus {
    outline: none;
  }
}
.fade-enter-active,
.fade-leave-active  {
  transition: transform 0.5s ease, opacity 0.5s ease;
}
.fade-leave-active {
  position: absolute;
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
  transform: translateY(10px);
}
</style>

