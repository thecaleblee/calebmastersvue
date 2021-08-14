<template>
  <hero v-bind="heroContent"></hero>
  <recent :content="recentContent"></recent>
  <skills :content="skillsContent"></skills>
  <resume :content="resumeContent"></resume>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import Hero from '@/components/Hero.vue'
import Recent from '@/components/Recent.vue'
import Skills from '@/components/Skills.vue'
import Resume from '@/components/Resume.vue';
import { RECENT } from '@/RecentData'
import { SKILLS } from '@/SkillsData'
import { RESUME } from '@/ResumeData'

export default defineComponent({
  name: 'Home',
  components: {
    Hero,
    Recent,
    Skills,
    Resume,
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
      resumeContent: RESUME,
    }
  }
});
</script>
