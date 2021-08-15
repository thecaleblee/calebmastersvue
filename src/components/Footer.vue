<template>
  <section>
    <footer>
      <slot></slot>
    </footer>
  </section>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'Footer',
})
</script>

<style lang="scss">
footer {
  flex-grow: 2;
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  padding: 2rem;
  overflow: hidden;

  * {
    position: relative;
    z-index: 5;
  }

  p {
    align-self: center;
  }
}

/* Footer */
footer {
  position: relative;
  background: var(--main-footer);
  color: var(--main-footer-text);
  margin-top: 2rem;
  padding-top: 1rem;
}

@media screen and (min-width: 567px) {
  footer {
    padding: 4rem 0 7rem;
    margin-bottom: 0;
    margin-top: 2rem;
  }
}

@media screen and (min-width: 905px) {
  footer {
    padding: 6rem 0;
  }
}


@media screen and (min-width: 1640px) {
  footer {
    padding: 8rem 0;
  }
}
</style>