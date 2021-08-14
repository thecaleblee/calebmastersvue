<template>
  <h4>I'm a skillbar {{name}} @ {{percent}}</h4>  

</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'SkillBar',
  props: {
    name: String,
    percent: String,
  }
})
</script>

<style lang="scss" scoped>

</style>