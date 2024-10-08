<script lang="ts">
  const socialLinks = [
    { name: 'GitHub', icon: '📂', url: 'https://github.com/yourusername' },
    { name: 'LinkedIn', icon: '💼', url: 'https://linkedin.com/in/yourusername' },
    { name: 'Twitter', icon: '🐦', url: 'https://twitter.com/yourusername' },
  ];
</script>

<footer>
  <div class="social-links">
    {#each socialLinks as link}
      <a href={link.url} target="_blank" rel="noopener noreferrer" class="social-link">
        <span class="icon">{link.icon}</span>
        <span class="name">{link.name}</span>
      </a>
    {/each}
  </div>
  <p>&copy; 2023 Your Name. All rights reserved.</p>
</footer>

<style>
  footer {
    margin-top: 2rem;
    text-align: center;
    padding: 1rem 0;
    border-top: 1px solid #ddd;
  }

  .social-links {
    display: flex;
    justify-content: center;
    gap: 1rem;
    margin-bottom: 1rem;
  }

  .social-link {
    display: flex;
    align-items: center;
    text-decoration: none;
    color: inherit;
    transition: transform 0.2s ease-in-out;
  }

  .social-link:hover {
    transform: translateY(-2px);
  }

  .icon {
    font-size: 1.2em;
    margin-right: 0.5rem;
  }

  @media (max-width: 768px) {
    .name {
      display: none;
    }
  }
</style>