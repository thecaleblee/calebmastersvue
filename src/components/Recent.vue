<template>
  <container :id="content.id">
    <h2>{{content.heading}}</h2>
    <card v-for="site in content.sites" v-bind="site" v-bind:key="site.id"></card> 
  </container>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import Container from './Container.vue'
import Card from './Card.vue' 

export default defineComponent({
  name: 'Recent',
  components: {
    Container,
    Card,
  },
  props: ['content']
})
</script>

<style lang="scss">
#recent-work {
  background: var(--main-bg);
  z-index: 2;

  h2 {
    color: var(--main-text);
    text-align: center;
    margin-bottom: 2rem;
    flex-basis: 100%;

    + a {
      flex-basis: 100%;
    }
  }

  .container {
    display: flex;
    flex: 1 1 100%;
    flex-flow: row wrap;
  }

  .top {
    margin-left: auto;
    margin-right: auto;
  }

  &:first-child a {
    margin-top: 2rem;
  }

  &:before {
    content: "";
    position: absolute;
    top: 0;
    bottom: 1%;
    right: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-image: linear-gradient(
      165deg,
      var(--main-theme),
      var(--main-subheading)
    );
    transform: skewY(2deg);
    transform-origin: 0;
    overflow: hidden;
  }
}

@media screen and (min-width: 567px) {
  #recent-work {
    h2 + a {
      margin-top: 0;
      flex: 1 calc(50% - 2rem);
    }

    .hide {
      display: none;
    }

    .top {
      margin-left: inherit;
      margin-right: inherit;
    }
  }
}

@media screen and (min-width: 784px) {
  #recent-work {
    h2 {
      margin-bottom: 4rem;
    }

    a,
    h2 + a {
      flex: 1 calc(33% - 2rem);
    }
  }
}

@media screen and (min-width: 905px) {
  #recent-work {
    h2 {
      margin-bottom: 5rem;
    }
  }
}

@media screen and (min-width: 970px) {
  #recent-work a:last-child {
    display: block;
    flex-basis: calc(33% - 2rem);
  }
}

</style>
