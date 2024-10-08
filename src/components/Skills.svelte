<script lang="ts">
  const skills = [
    { name: 'JavaScript/TypeScript', icon: '🟨' },
    { name: 'React', icon: '⚛️' },
    { name: 'Svelte', icon: '🔶' },
    { name: 'Node.js', icon: '🟩' },
    { name: 'Express', icon: '🚂' },
    { name: 'MongoDB', icon: '🍃' },
    { name: 'SQL', icon: '🗄️' },
    { name: 'HTML/CSS', icon: '🎨' },
  ];
</script>

<section id="skills">
  <h2>Skills</h2>
  <ul>
    {#each skills as skill}
      <li>
        <span class="icon">{skill.icon}</span>
        {skill.name}
      </li>
    {/each}
  </ul>
</section>

<style>
  section {
    padding: 2rem 0;
    background-color: #f9f9f9;
    border-radius: 8px;
    margin: 2rem 0;
  }

  h2 {
    text-align: center;
    margin-bottom: 1.5rem;
    color: #333;
  }

  ul {
    display: flex;
    flex-wrap: wrap;
    gap: 1rem;
    padding: 0;
    list-style-type: none;
    justify-content: center;
  }

  li {
    background-color: #ffffff;
    padding: 0.75rem 1.25rem;
    border-radius: 30px;
    display: flex;
    align-items: center;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
    transition: transform 0.2s ease-in-out;
  }

  li:hover {
    transform: translateY(-3px);
  }

  .icon {
    margin-right: 0.5rem;
    font-size: 1.2em;
  }

  :global(.dark) section {
    background-color: #2a2a2a;
  }

  :global(.dark) li {
    background-color: #3a3a3a;
    color: #ffffff;
  }

  :global(.dark) h2 {
    color: #ffffff;
  }
</style>