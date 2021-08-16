<template>
  <section :id="id">
    <div class="container">
      <slot></slot>
      <a
        href="#top"
        to="top"
        aria-label="Back to Top"
        class="top"
      >
        Back to Top
      </a>
    </div>
  </section>
</template>
<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'Container',
  props: {
    id: String,
  }
})
</script>
