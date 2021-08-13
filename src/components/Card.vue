<template>
  <a :href="link" :aria-label="al">
    <article>
      <hgroup>
        <h3 :aria-label="heading" itemProp="title">
          {{ heading }}
        </h3>
        <h4 :item-prop="subheading">
          <span>{{ subheading }} </span>
          <template v-for="(item, idx) in techStack" :key="item">
            {{ item.name }}<span v-if="idx + 1 === techStack.length">.</span><span v-else>,</span>
          </template>
        </h4>
      </hgroup>
      <p>{{ description }}</p>
    </article>
  </a>
</template>

vue <script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'Card',
  props: { 
    al: String,
    link: String,
    background: String,
    heading: String,
    subheading: String,
    techStack: Array,
    description: String,
  },
})
</script>

<style lang="scss" scoped>
  a {
    transition: all 300ms cubic-bezier(0.46, 0.03, 0.52, 0.96);
    padding: 12rem 1rem 1rem;
    margin: 0 1rem 2rem;
    background: var(--main-bg);
    border: 1px solid var(--tertiary-text);
    border-radius: 0.3rem;
    position: relative;
    overflow: hidden;
    text-decoration: none;

    h3 {
      color: var(--main-heading);
      margin-bottom: 1rem;
    }

    p {
      color: var(--secondary-text);
      margin-top: 2rem;
      font-size: 1.5rem;
    }
    
    &.top {
      padding: 1rem;
      margin: 2rem 0 0;
      background: unset;
      border: none;
      flex-basis: 100%;
      color: var(--main-text);
      text-decoration: underline;

      &:hover,
      &:focus,
      &:active {
        box-shadow: none;
        text-decoration: none;
      }

      &:visited {
        color: var(--main-text);
      }

      &:before {
        display: none;
      }
    }

    &::before {
      border-bottom: 1px solid var(--tertiary-text);
      position: absolute;
      top: 0;
      height: 10rem;
      left: 0;
      right: 0;
      display: block;
      content: "";
      background: no-repeat center center var(--background);
      background-size: cover;
    }

    &.this-website::before {
      background: no-repeat 50% 20% var(--background);
      background-size: cover;
    }

    &:focus,
    &:active,
    &:hover {
      box-shadow: 0 0 0.8rem 0 var(--main-heading);
      filter: opacity(90%) saturate(1.2);
    }
  }

@media screen and (min-width: 415px) {
  a {
    flex: 2 1 calc(50% - 2rem);

    &.top {
      padding-right: 1.5rem;
    }
  }
}

@media screen and (min-width: 567px) {
  a,
  h2 + a {
    margin-top: 0;
    flex: 1 calc(50% - 2rem);
  }

  .hide {
    display: none;
  }
}

@media screen and (min-width: 784px) {
  a {
    flex: 1 calc(33% - 2rem);
    align-items: stretch;

    &:last-child {
      align-self: flex-end;
    }
  }
}

@media screen and (min-width: 905px) {
  a {
    padding-top: 24rem;

    &:before {
      height: 20rem;
    }

    p {
      font-size: 1.7rem;
    }
  }
}

@media screen and (min-width: 970px) {
  a:last-child {
    display: block;
    flex-basis: 33%;
  }
}
</style>