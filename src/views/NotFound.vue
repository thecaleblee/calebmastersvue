<template>
  <section id="hero" class="page">
    <div class="container">
      <h1>
        Yikes! <span>404</span>
      </h1>
      <a href="/" aria-label="Go to HomePage">Back to Saftey</a>
      <article>
        <div>
          <h3 aria-label="Page Unavailable" item-prop="title">
            Page Unavailable
          </h3>
          <h4 item-prop="subheading"></h4>
        </div>
        <p>
          It's just as likely this page <i>should</i> exist and I just
          haven't built it yet. Or it's a typo. Or, I dunno, aliens?
        </p>
      </article>
    </div>
  </section>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import Container from '@/components/Container.vue'

export default defineComponent({
  name: 'NotFound',
  components: {
    Container,
  }
})
</script>

<style lang="scss" scoped>
#hero {
  min-height: 30vh;
  display: flex;
  flex-direction: row;
  justify-content: center;
  text-align: center;
  letter-spacing: 0.1rem;

  .container {
    display: flex;
    flex-direction: column;
  }

  h1 {
    font-family: "Montserrat";
    font-size: 5rem;
    line-height: 1;
    margin-bottom: 2.5rem;

    span {
      display: block;
      background-image: linear-gradient(
        var(--main-theme),
        var(--main-subheading)
      );
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }
  }

  &.page {
    padding-bottom: 8rem;
    min-height: 0;

    article { 
      margin-top: 4rem;
      max-width: 80vw;
    }
  }
}

@media screen and (min-width: 567px) {
  #hero {
    h1 {
      font-size: 6.5rem;
    }
  }
}

@media screen and (min-width: 905px) {
  #hero {
    min-height: 60rem;

    h1 {
      font-size: 9rem;

      span {
        display: inline;
      }
    }

    &.page article {
      max-width: 65rem;
    }
  }
}
</style>