<template>
  <hero v-bind="heroContent"></hero>
  <recent :content="recentContent"></recent>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import Hero from '@/components/Hero.vue'
import Recent from '@/components/Recent.vue'
import { RECENT } from '@/RecentData'
import { SKILLS } from '@/SkillsData'

export default defineComponent({
  name: 'Home',
  components: {
    Hero,
    Recent,
  },
  data() {
    return {
      heroContent: {
        id: 'hero',
        tagline: 'portfolio for',
        emHeading: 'Caleb',
        heading: 'Masters',
        talkingPoints: ['Front-End Engineer.', 'UX Promoter.', 'Hobby Collector.'],
      },
      recentContent: RECENT,
      skillsContent: SKILLS,
    }
  }
});
</script>
