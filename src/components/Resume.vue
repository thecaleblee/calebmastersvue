<template>
  <container :id="content.id">
    <h2>
      {{content.heading}}
      <span>{{content.subheading}}</span>
    </h2>
    <article>
      <header>
        <h2>
          {{content.title}}
          <span>
            <a :href="content.downloadUrl" :aria-label="content.downloadText">
              {{content.downloadText}}
            </a>
          </span>
        </h2>
        <p>{{content.contactText}}</p>
        <p>
          <a :href="content.url" :aria-label="content.al" target="_blank" rel="noopener">
            {{content.urlText}}
          </a>
        </p>
        <p>{{content.location}}</p>
      </header>
      <section>
        <h3>Summary</h3>
        <p>{{content.summary}}</p>
      </section>
    </article>
  </container>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import Container from './Container.vue'
import Axios from 'axios';

export default defineComponent({
  name: 'Resume',
  props: ['content'],
  components: {
    Container,
  }
})
</script>

<style lang="scss">
#resume {
  background-color: var(--tertiary-bg);
  color: var(--main-heading);

  h2 {
    color: var(--main-heading);
    margin-bottom: 2rem;

    a {
      background: var(--main-heading);
      color: var(--main-bg);
      padding: 0.5rem 1rem;
      text-transform: uppercase;
      text-decoration: none;
      font-size: 3rem;

      &:hover {
        background: var(--main-subheading);
        color: var(--main-bg);
      }
    }
  }

  section {
    a {
      font-family: "Montserrat";
      color: var(--main-text);

      &:visited {
        color: var(--main-text);
      }

      &.active,
      &:hover {
        color: var(--main-theme);
        text-decoration: none;
      }
    }
  }

  .container {
    flex-direction: column;
    text-align: center;
    z-index: 5;
  }

  article {
    background: var(--main-bg);
    border: 1px solid var(--tertiary-text);
    border-radius: 0.3rem;
    box-shadow: 0 0.8rem 0.8rem rgb(51 66 64 / 40%);
    display: grid;
    grid-gap: 4rem;
    margin: 1rem 1rem 0;
    padding: 1rem;
    text-align: left;

    section {
      padding: 0;

      section,
      p {
        padding: 0 2rem;
      }
    }

    header {
      display: grid;
      grid-template-rows: auto;
      text-align: center;
    }

    section {
      h4 {
        font-weight: bold;
        margin-top: 1rem;

        span {
          display: block;
        }
      }

      h5 {
        font-weight: bold;
      }
    }

    ul {
      margin-left: 2rem;
      font-size: 1.6rem;
      list-style-type: circle;

      li {
        margin-bottom: 1rem;
      }
    }
  }

  article + p {
    margin-top: 4rem;
  }

  a.top {
    padding: 1rem;
    flex-basis: 100%;
    color: var(--main-text);
    text-decoration: underline;

    &:hover {
      box-shadow: none;
      text-decoration: none;
    }

    &:visited {
      color: var(--main-text);
    }
  }
  
  &::before {
    background-color: var(--tertiary-bg);
    content: "";
    position: absolute;
    top: 0;
    bottom: 0;
    right: 0;
    left: 0;
    height: 100%;
    width: 100%;
    overflow: hidden;
    transform: skewY(-3deg);
    transform-origin: 0;
    z-index: 4;
  }

  &::after {
    background-color: var(--tertiary-bg);
    content: "";
    position: absolute;
    top: 0;
    bottom: 0;
    right: 0;
    left: 0;
    height: 100%;
    width: 100%;
    overflow: hidden;
    transform: skewY(-3deg);
    transform-origin: 0;
    z-index: 4;
    bottom: -2rem;
    top: unset;
    background-color: var(--main-footer);
    transform: skewY(1.5deg);
    height: 3rem;
  }
}

@media screen and (min-width: 415px) {
  #resume {
    a.top {
      padding-right: 1.5rem;
    }
  }
}

@media screen and (min-width: 567px) {
  #resume {
    padding-bottom: 10rem;

    &::after {
      bottom: -2rem;
      height: 5rem;
    }
  }
}

@media screen and (min-width: 784px) {
  #resume article section h4 span {
    width: 20%;
    float: right;
    text-align: right;
  }
}

@media screen and (min-width: 905px) {
  #resume {
    padding: 9rem 0 11rem;
  }
}

@media screen and (min-width: 970px) {
  #resume {
    padding: 4rem;

    h2 a {
      font-size: 3.4rem;
    }

    article {
      background: var(--main-bg);
      border: 1px solid var(--tertiary-text);
      border-radius: 0.3rem;
      box-shadow: 0 0.8rem 0.8rem rgb(51 66 64 / 40%);
      display: grid;
      grid-gap: 4rem;
      margin: 1rem 1rem 0;
      padding: 4rem;
      text-align: left;

      section {
        padding: 0;
        text-align: justify;

        section,
        p {
          padding: 0 2rem;
        }
      }

      header {
        display: grid;
        grid-template-columns: repeat(6, 1fr);
        grid-template-rows: auto;
        grid-template-areas:
          "t t t t t t"
          "m1 m1 m2 m2 m3 m3";
        text-align: center;

        h2 {
          grid-area: t / span 6;
        }

        p {
          grid-area: m1;

          + p {
            grid-area: m2 / span 2;

            + p {
              grid-area: m3;
            }
          }
        }
      }

      section {
        h4 {
          font-weight: bold;
          margin-top: 1rem;

          span {
            width: 20%;
            float: right;
            text-align: right;
          }
        }

        h5 {
          font-weight: bold;
        }
      }

      ul {
        margin-left: 2rem;
        font-size: 1.6rem;
        list-style-type: circle;
      }
    }
  }
}

@media screen and (min-width: 1100px) {
  #resume {
    padding: 13rem 0 15rem;
  }
}

@media screen and (min-width: 1640px) {
  #resume {
    padding: 17rem 0 19rem;

    h2 a {
      font-size: 4rem;
    }
  }
}
</style>
