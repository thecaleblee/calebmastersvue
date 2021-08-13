<template>
  <hero v-bind="content"></hero>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import Hero from '@/components/Hero.vue';
interface Content {
  id: String, 
  tagline: String,
  emHeading: String, 
  heading: String, 
  talkingPoints: Array<String>,
}

export default defineComponent({
  name: 'Home',
  components: {
    Hero,
  },
  data() {
    return {
      content: {
        id: 'hero',
        tagline: 'portfolio for',
        emHeading: 'Caleb',
        heading: 'Masters',
        talkingPoints: ['Front-End Engineer.', 'UX Promoter.', 'Hobby Collector.'],
      } as Content
    }
  }
});
</script>
