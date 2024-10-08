<script lang="ts">
  import { onMount } from 'svelte';
  import type { Writable } from 'svelte/store';

  export let darkMode: Writable<boolean>;
  export let toggleDarkMode: () => void;

  let menuOpen = false;
  let isMobile = false;

  function toggleMenu() {
    menuOpen = !menuOpen;
  }

  function closeMenu() {
    menuOpen = false;
  }

  onMount(() => {
    const checkMobile = () => {
      isMobile = window.innerWidth <= 768;
    };
    checkMobile();
    window.addEventListener('resize', checkMobile);
    return () => window.removeEventListener('resize', checkMobile);
  });
</script>

<header>
  <div class="logo">Your Logo</div>
  <nav class:open={menuOpen}>
    <ul>
      <li><a href="#about" on:click={closeMenu}>Acerca de min</a></li>
      <li><a href="#projects" on:click={closeMenu}>Proyectos</a></li>
      <li><a href="#skills" on:click={closeMenu}>Skills</a></li>
      <li><a href="#contact" on:click={closeMenu}>Contacto</a></li>
    </ul>
  </nav>
  <div class="right-section">
    <button on:click={toggleDarkMode} class="theme-toggle">
      {$darkMode ? '☀️' : '🌙'}
    </button>
    {#if isMobile}
      <button on:click={toggleMenu} class="menu-toggle">
        {menuOpen ? '✖' : '☰'}
      </button>
    {/if}
  </div>
</header>

<style>
  header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem;
    position: sticky;
    top: 0;
    background-color: inherit;
    z-index: 1000;
    box-shadow: 0 2px 4px rgba(0,0,0,0.1);
  }

  .logo {
    font-size: 1.5rem;
    font-weight: bold;
  }

  nav ul {
    display: flex;
    list-style-type: none;
    padding: 0;
    margin: 0;
  }

  nav li {
    margin-right: 1rem;
  }

  nav a {
    text-decoration: none;
    color: inherit;
  }

  .right-section {
    display: flex;
    align-items: center;
  }

  button {
    background: none;
    border: none;
    font-size: 1.5rem;
    cursor: pointer;
    padding: 0.5rem;
  }

  .menu-toggle {
    display: none;
  }

  @media (max-width: 768px) {
    nav {
      position: absolute;
      top: 100%;
      left: 0;
      right: 0;
      background-color: inherit;
      box-shadow: 0 2px 4px rgba(0,0,0,0.1);
      display: none;
    }

    nav.open {
      display: block;
    }

    nav ul {
      flex-direction: column;
    }

    nav li {
      margin: 0;
      text-align: center;
    }

    nav a {
      display: block;
      padding: 1rem;
    }

    .menu-toggle {
      display: block;
    }
  }
</style>