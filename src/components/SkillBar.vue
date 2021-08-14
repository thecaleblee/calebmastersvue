<template> 
  <p :aria-label="name + percent + '%'">{{name}}<span :style="cssVars">{{name}}</span></p>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'SkillBar',
  props: {
    name: String,
    percent: String,
  },
  computed: {
    cssVars() {
      return {
        '--bar-width' : this.percent,
        '--bar-content': this.name,
      }
    }
  }
})
</script>

<style lang="scss" scoped>
  p span {
    background-image: linear-gradient(
      90deg,
      var(--main-subheading),
      var(--main-theme)
    );
    color: var(--main-text);
    border-radius: 5px 4px 4px 5px;
    content: var(--skill-text);
    text-align: right;
    position: absolute;
    padding-right: 1rem;
    top: 0;
    bottom: 0;
    right: 0;
    left: 0;
    width: var(--percent);
    height: 100%;
    z-index: -1;
  }
  p span {
    display: block;
    content: var(--bar-content);
    width: var(--bar-width);
    height: 100%;
  }
</style>