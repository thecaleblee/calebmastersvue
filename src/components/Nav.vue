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
          <a href="#skills" aria-label="Skills">
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
            href="/"
            class="active"
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

<style>
nav {
	display: flex;
	flex-flow: column wrap;
	justify-content: space-between;
	padding-top: 1rem;
}

nav img {
	max-height: 3rem;
}

nav ul {
	display: flex;
	flex-direction: row;
	justify-content: space-around;
	align-items: flex-start;
	margin: 0;
}

nav .tech {
	font-size: 1rem;
	color: var(--main-footer-link);
	background: var(--secondary-text);
	justify-content: space-evenly;
	padding: 0.3rem 0;
}

nav .tech a {
	color: var(--tertiary-bg);
	text-decoration: none;
}

nav .tech a.active, nav .tech a:hover {
	border-bottom: 1px dotted var(--main-bg);
}

nav ul:first-child i {
	margin-right: 1rem;
}

nav ul:first-child a {
	font-family: "Montserrat";
	color: var(--main-text);
	display: flex;
	flex-direction: column-reverse;
	align-items: center;
}

nav ul:first-child a:visited {
	font-family: "Montserrat";
	color: var(--main-text);
}

nav ul:first-child a.active, nav ul:first-child a:hover {
	color: var(--main-theme);
	text-decoration: none;
}

nav ul:first-child a.active i, nav ul:first-child a:hover i {
	color: var(--main-theme);
}

nav ul:first-child a.active i.gg-browser::before, nav ul:first-child a.active i.gg-browser::after, nav ul:first-child a:hover i.gg-browser::before, nav ul:first-child a:hover i.gg-browser::after {
	background: var(--main-theme);
}

nav ul:first-child a.active i.gg-terminal::after, nav ul:first-child a:hover i.gg-terminal::after {
	background: var(--main-theme);
}
</style>