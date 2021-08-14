<template>
  <section :id="content.id">
    <div class="container">
      <h2>
        {{content.heading}}
        <span>{{content.subheading}}</span>
      </h2>
      <article :aria-label="content.al">
        <template v-for="skill of content.skillSet" v-bind:key="skill.category">
          <h3>{{skill.category}}</h3>
          <skill-bar v-for="bar of skill.skills" v-bind="bar" v-bind:key="bar.name"></skill-bar>
        </template>
      </article>
      </div>
  </section>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import SkillBar from './SkillBar.vue'

export default defineComponent({
  name: 'Skills',
  components: {
    SkillBar,
  },
  props: ['content']
})
</script>

<style lang="scss" scoped>

</style>