<template>
  <hero :id="id" :tagline="tagline" :emHeading="emHeading" :heading="heading" :talkingPoints="talkingPoints"></hero>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import Hero from '@/components/Hero.vue';

export default defineComponent({
  name: 'Home',
  components: {
    Hero,
  },
  data() {
    return {
      id: 'hero',
      tagline: 'portfolio for',
      emHeading: 'Caleb',
      heading: 'Masters',
      talkingPoints: ['Front-End Engineer.', 'UX Promoter.', 'Hobby Collector.'],
    }
  }
});
</script>
