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
/* Skills */
#skills {
  background-color: var(--alt-secondary-bg);
  color: var(--alt-secondary-text);

  .container {
    flex-direction: column;
    text-align: center;
  }

  h2 {
    color: var(--alt-main-theme);
    margin-bottom: 2rem;
  }

  article {
    background-color: var(--main-text);
    border: 1px solid var(--main-heading);
    border-radius: 0.4rem;
    padding: 2rem;
    display: grid;
    grid-template-columns: 1fr;
    grid-gap: 2rem;
  }

  p {
    font-size: 1.5rem;
    line-height: 1.7;
    position: relative;
    display: block;
    border-radius: 0.6rem;
    background: var(--secondary-text);
    border: 1px solid var(--tertiary-text);
    text-align: left;
    padding-left: 1rem;
    color: var(--main-text);
    z-index: 2;
    font-weight: 500;
    color: transparent; 
  }

  .top {
    padding: 1rem;
    margin: 2rem 0 0;
    flex-basis: 100%;
    color: var(--main-bg);
    text-decoration: underline;

    &:hover {
      text-decoration: none;
    }

    &:visited {
      color: var(--main-bg);
    }
  }
}


@media screen and (min-width: 567px) {
#skills {
    .container {
      padding: 1rem;
    }

    article {
      grid-template-columns: calc(50% - 1rem) calc(50% - 1rem);
    }

    h3 {
      grid-column: span 2;
    }
  }
}


</style>