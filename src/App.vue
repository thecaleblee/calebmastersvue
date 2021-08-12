<template>
  <div id="top">
    <Nav></Nav> 
  </div>
  <router-view/>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import Nav from '@/components/Nav.vue'

export default defineComponent({
  components: {
    Nav,
  }
})
</script>


<style>
* {
  box-sizing: border-box;
}

*::before,
*::after {
  box-sizing: border-box;
}

html {
  font-size: 62.5%;
}

body,
h1,
h2,
h3,
h4,
h5,
h6,
p {
  margin: 0;
  font-weight: normal;
}

ul,
ol {
  padding: 0;
}

/* montserrat-900 - latin */
@font-face {
  font-family: "Montserrat";
  font-style: normal;
  font-weight: 900;
  font-display: swap;
  src: url("./assets/fonts/montserrat-v15-latin-900.eot"); /* IE9 Compat Modes */
  src: local(""),
    url("./assets/fonts/montserrat-v15-latin-900.eot?#iefix")
      format("embedded-opentype"),
    /* IE6-IE8 */ url("./assets/fonts/montserrat-v15-latin-900.woff2") format("woff2"),
    /* Super Modern Browsers */ url("./assets/fonts/montserrat-v15-latin-900.woff")
      format("woff"),
    /* Modern Browsers */ url("./assets/fonts/montserrat-v15-latin-900.ttf")
      format("truetype"),
    /* Safari, Android, iOS */
      url("./assets/fonts/montserrat-v15-latin-900.svg#Montserrat") format("svg"); /* Legacy iOS */
}

body {
  min-height: 100vh;
  scroll-behavior: smooth;
  text-rendering: optimizeSpeed;
  font-size: 17px;
  font-size: 1.7rem;
  line-height: 1.5;
  font-display: optional;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
    Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
}

ol,
ul {
  list-style-type: none;
}

img {
  max-width: 100%;
  height: auto;
  border: none;
}

/* Variables */
:root {
  --main-bg: #fff;
  --main-theme: #129fa8;
  --main-heading: #0f5b46;
  --main-subheading: #13a895;
  --main-text: #292f2d;
  --main-footer: var(--main-text);
  --main-footer-link: #aaacab;
  --main-footer-text: var(--alt-secondary-text);
  --secondary-bg: #d5ede6;
  --secondary-text: #434b49;
  --tertiary-bg: #ecf7f2;
  --tertiary-text: #555a59;
  --alt-main-bg: var(--main-text);
  --alt-main-theme: #15bdc8;
  --alt-secondary-bg: #334240;
  --alt-secondary-text: #9fcfc8;
}

/* Icons for Nav from css.gg */
.gg-browser {
  box-sizing: border-box;
  position: relative;
  display: block;
  transform: scale(var(--ggs, 0.7));
  width: 24px;
  height: 18px;
  border: 2px solid;
  border-radius: 3px;
  color: var(--main-text);
}

  .gg-browser::after,
  .gg-browser::before {
    content: "";
    display: block;
    box-sizing: border-box;
    position: absolute;
    width: 22px;
    height: 2px;
    background: var(--main-text);
    top: 4px;
  }

  .gg-browser::after {
    border-radius: 3px;
    width: 2px;
    box-shadow: 3px 0 0, 6px 0 0;
    top: 1px;
    left: 1px;
  }

.gg-briefcase {
  color: var(--main-text);
  box-sizing: border-box;
  position: relative;
  display: block;
  transform: scale(var(--ggs, 0.8));
  width: 22px;
  height: 16px;
  border: 2px solid;
  border-radius: 2px;
  margin-top: 1px;
}

  .gg-briefcase::after {
    content: "";
    display: block;
    box-sizing: border-box;
    position: absolute;
  }

  .gg-briefcase::before {
    content: "";
    display: block;
    box-sizing: border-box;
    position: absolute;
    border: 2px solid;
    border-top-left-radius: 1px;
    border-top-right-radius: 1px;
    left: 4px;
    width: 10px;
    height: 4px;
    border-bottom: 0;
    top: -5px;
  }

  .gg-briefcase::after {
    width: 18px;
    height: 3px;
    border-left: 7px solid transparent;
    border-right: 7px solid transparent;
    border-bottom: 1px solid transparent;
    box-shadow: 0 2px 0, inset 16px 74px 0;
    top: 4px;
  }

.gg-terminal {
  color: var(--main-text);
  box-sizing: border-box;
  position: relative;
  display: block;
  transform: scale(var(--ggs, 0.7));
  width: 24px;
  height: 20px;
  border: 2px solid;
  border-radius: 2px;
}

  .gg-terminal::after {
    content: "";
    display: block;
    box-sizing: border-box;
    position: absolute;
  }

  .gg-terminal::before {
    content: "";
    display: block;
    box-sizing: border-box;
    position: absolute;
    border-right: 2px solid;
    border-bottom: 2px solid;
    transform: rotate(-45deg);
    width: 6px;
    height: 6px;
    top: 5px;
    left: 3px;
  }

  .gg-terminal::after {
    width: 4px;
    height: 2px;
    background: var(--main-text);
    top: 10px;
    left: 11px;
  }

.gg-link {
  box-sizing: border-box;
  position: relative;
  display: inline-block;
  transform: rotate(-45deg) scale(var(--ggs, 1));
  width: 8px;
  height: 2px;
  background: currentColor;
  border-radius: 4px;
  vertical-align: middle;
  margin-left: 0.5rem;
}

.gg-link::after,
.gg-link::before {
  content: "";
  display: block;
  box-sizing: border-box;
  position: absolute;
  border-radius: 3px;
  width: 8px;
  height: 10px;
  border: 2px solid;
  top: -4px;
}

.gg-link::before {
  border-right: 0;
  border-top-left-radius: 40px;
  border-bottom-left-radius: 40px;
  left: -6px;
}

.gg-link::after {
  border-left: 0;
  border-top-right-radius: 40px;
  border-bottom-right-radius: 40px;
  right: -6px;
}
/* #app { */
  /* font-family: Avenir, Helvetica, Arial, sans-serif; */
  /* -webkit-font-smoothing: antialiased; */
  /* -moz-osx-font-smoothing: grayscale; */
  /* text-align: center; */
  /* color: #2c3e50; */
/* } */

.container {
  position: relative;
}

section {
  width: 100%;
}
/* Styles for layout */
#app {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  height: auto;
  color: var(--main-text);
  background: var(--main-bg);
}

/* Typography */
h1 {
  font-size: 3.5rem;
}

h2 {
  font-size: 2.8rem;
}

h3 {
  font-size: 2.2rem;
}

h4 {
  font-size: 1.7rem;
}

h1,
h2,
h3 {
  font-family: "Montserrat";
}

h2 span {
  font-size: 1.7rem;
  display: block;
  text-align: center;
  font-weight: normal;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
    Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
}


h4 {
  color: var(--tertiary-text);
}

h4 span {
  color: var(--main-heading);
  font-size: 1.5rem;
}

/* Global Styling */
section {
  padding: 6rem 1rem;
  margin: 0;
  position: relative;
}

article + article {
  margin-top: 1.5rem;
}

.top {
  display: block;
  margin-top: 2rem;
  text-align: center;
}
</style>
