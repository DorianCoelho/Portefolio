<script lang="ts">
  import { writable } from 'svelte/store';
  import Header from './components/Header.svelte';
  import About from './components/About.svelte';
  import Projects from './components/Projects.svelte';
  import Skills from './components/Skills.svelte';
  import Contact from './components/Contact.svelte';
  import Footer from './components/Footer.svelte';

  const darkMode = writable(false);

  function toggleDarkMode() {
    darkMode.update(value => !value);
  }
</script>

<main class:dark={$darkMode}>
  <Header {darkMode} {toggleDarkMode} />
  <div class="content">
    <About />
    <Projects />
    <Skills />
    <Contact />
  </div>
  <Footer />
</main>

<style>
  :global(body) {
    margin: 0;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    transition: background-color 0.3s, color 0.3s;
  }

  main {
    max-width: 1200px;
    margin: 0 auto;
    background-color: #ffffff;
    color: #333333;
  }

  .content {
    padding: 20px;
  }

  main.dark {
    background-color: #1a1a1a;
    color: #ffffff;
  }

  :global(h2) {
    font-size: 2.5em;
    margin-bottom: 1em;
  }

  :global(section) {
    margin-bottom: 3em;
  }
</style>