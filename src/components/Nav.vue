<template>
  <header>
    <nav role="navigation" aria-label="Main Navigation">
      <ul>
        <li>
          <a href="/" aria-label="Home">
            <img
              src="https://res.cloudinary.com/calebmastersdev/image/upload/v1620762551/cmdev/cmlogo-t_aavg64.png"
              alt="Caleb Masters Dev"
              width="55"
              height="30"
            />
          </a>
        </li>
        <li>
          <a href="#recent-work" aria-label="Recent Work">
            <i class="gg-browser"></i>
            Recent Work
          </a>
        </li>
        <li>
          <a href="#skills" aria-label="Skills" @click="scrollTo">
            <i class="gg-terminal"></i>
            Skills
          </a>
        </li>
        <li>
          <a href="#resume" aria-label="Resumé">
            <i class="gg-briefcase"></i>
            Resumé
          </a>
        </li>
      </ul>
      <ul class="tech" aria-hidden="true">
        <li>
          <a
            href="https://calebmasters.dev"
            aria-label="Change Website Tech Stack to: HTML/CSS/JS"
            >HTML/CSS/JS</a
          >
        </li>
        <li>
          <a
            href="https://react.calebmasters.dev/"
            aria-label="Change Website Tech Stack to: React/Next.js"
            >React/Next.js</a
          >
        </li>
        <li>
          <a
            href="https://ng.calebmasters.dev/"
            aria-label="Change Website Tech Stack to: Angular.js/SCSS"
            >Angular.js/SCSS</a
          >
        </li>
        <li>
          <a
            href="/"
            aria-disabled="true"
            class="active"
            @click.prevent
            aria-label="Change Website Tech Stack to: Vue.js/SCSS/TS"
            >Vue.js/TS/SCSS</a
          >
        </li>
      </ul>
    </nav>
  </header>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'Nav',
  props: {
    // msg: String,
  },
});
</script>

<style lang="scss" scoped>
nav {
  display: flex;
  flex-flow: column wrap;
  justify-content: space-between;
  padding-top: 1rem;

  img {
    max-height: 3rem;
    margin-bottom: .2rem;
  }

  ul {
    display: flex;
    flex-direction: row;
    justify-content: space-around;
    align-items: flex-start;
    margin: 0;
  }

  .tech {
    font-size: 1rem;
    color: var(--main-footer-link);
    background: var(--secondary-text);
    justify-content: space-evenly;
    padding: 0.3rem 0;

    a {
      color: var(--tertiary-bg);
      text-decoration: none;

      &.active,
      &:hover {
        border-bottom: 1px dotted var(--main-bg);
      }
    }
  }

  ul:first-child {
    i {
      margin-right: 1rem;
    }

    a {
      font-family: "Montserrat";
      color: var(--main-text);
      display: flex;
      flex-direction: column-reverse;
      align-items: center;

      &:visited {
        font-family: "Montserrat";
        color: var(--main-text);
      }

      &.active,
      &:hover {
        color: var(--main-theme);
        text-decoration: none;

        i {
          color: var(--main-theme);

          &.gg-browser {
            &::before,
            &::after {
              background: var(--main-theme);
            }
          }
          &.gg-terminal::after {
            background: var(--main-theme);
          }
        }
      }
    }
  }
}

.gg-browser {
  box-sizing: border-box;
  position: relative;
  display: block;
  transform: scale(var(--ggs, 0.7));
  width: 24px;
  height: 18px;
  border: 2px solid;
  border-radius: 3px;
  color: var(--main-text);

  &::after,
  &::before {
    content: "";
    display: block;
    box-sizing: border-box;
    position: absolute;
    width: 22px;
    height: 2px;
    background: var(--main-text);
    top: 4px;
  }

  &::after {
    border-radius: 3px;
    width: 2px;
    box-shadow: 3px 0 0, 6px 0 0;
    top: 1px;
    left: 1px;
  }
}

.gg-briefcase {
  color: var(--main-text);
  box-sizing: border-box;
  position: relative;
  display: block;
  transform: scale(var(--ggs, 0.8));
  width: 22px;
  height: 16px;
  border: 2px solid;
  border-radius: 2px;
  margin-top: 1px;

  &::after {
    content: "";
    display: block;
    box-sizing: border-box;
    position: absolute;
  }

  &::before {
    content: "";
    display: block;
    box-sizing: border-box;
    position: absolute;
    border: 2px solid;
    border-top-left-radius: 1px;
    border-top-right-radius: 1px;
    left: 4px;
    width: 10px;
    height: 4px;
    border-bottom: 0;
    top: -5px;
  }

  &::after {
    width: 18px;
    height: 3px;
    border-left: 7px solid transparent;
    border-right: 7px solid transparent;
    border-bottom: 1px solid transparent;
    box-shadow: 0 2px 0, inset 16px 74px 0;
    top: 4px;
  }
}

.gg-terminal {
  color: var(--main-text);
  box-sizing: border-box;
  position: relative;
  display: block;
  transform: scale(var(--ggs, 0.7));
  width: 24px;
  height: 20px;
  border: 2px solid;
  border-radius: 2px;

  &::after {
    content: "";
    display: block;
    box-sizing: border-box;
    position: absolute;
  }

  &::before {
    content: "";
    display: block;
    box-sizing: border-box;
    position: absolute;
    border-right: 2px solid;
    border-bottom: 2px solid;
    transform: rotate(-45deg);
    width: 6px;
    height: 6px;
    top: 5px;
    left: 3px;
  }

  &::after {
    width: 4px;
    height: 2px;
    background: var(--main-text);
    top: 10px;
    left: 11px;
  }
}

.gg-link {
  box-sizing: border-box;
  position: relative;
  display: inline-block;
  transform: rotate(-45deg) scale(var(--ggs, 1));
  width: 8px;
  height: 2px;
  background: currentColor;
  border-radius: 4px;
  vertical-align: middle;
  margin-left: 0.5rem;

  &::after,
  &::before {
    content: "";
    display: block;
    box-sizing: border-box;
    position: absolute;
    border-radius: 3px;
    width: 8px;
    height: 10px;
    border: 2px solid;
    top: -4px;
  }

  &::before {
    border-right: 0;
    border-top-left-radius: 40px;
    border-bottom-left-radius: 40px;
    left: -6px;
  }

  &::after {
    border-left: 0;
    border-top-right-radius: 40px;
    border-bottom-right-radius: 40px;
    right: -6px;
  }
}

@media screen and (min-width: 415px) {
  nav ul:first-child li a {
    flex-direction: row;
  }
}

@media screen and (min-width: 567px) {
  nav {
    background: var(--main-bg);
    box-shadow: 0 0 3px rgb(0 0 0 / 30%);
    flex-direction: column-reverse;
    padding-top: 0;
    padding-bottom: .5rem;
    position: fixed;
    width: 100%;
    z-index: 9999;

    img {
      margin-bottom: 0;
      margin-top: .2rem;
    }

    &.tech {
    margin-bottom: 1rem;
    justify-content: flex-end;

      a {
        margin-right: 2rem;
      }
    }
  }
}

@media screen and (min-width: 784px) {
  nav ul:first-child li {
    font-size: 2rem;
  }
}

@media screen and (min-width: 905px) {
  nav img {
    justify-self: flex-start; 
  }
}

@media screen and (min-width: 1100px) {
  nav ul:first-child li {
    font-size: 2.2rem;
  }
}

@media screen and (min-width: 1640px) {
  nav ul:first-child li {
    font-size: 2.4rem;
  }
}
</style>
