<script lang="ts">
  const projects = [
    {
      title: 'Rs-jobs',
      description: 'Portal hecho con .net y razor pages',
      image: 'https://i.ibb.co/TbQ7wVr/Screenshot-2024-10-08-at-23-34-15.png',
      url: 'https://app.rs-jobs.com'
    },
    {
      title: 'Project 2',
      description: 'An e-commerce platform using Svelte and MongoDB',
      image: 'https://via.placeholder.com/400x300.png?text=Project+2',
      url: '#'
    },
    {
      title: 'Project 3',
      description: 'A real-time chat application with Socket.io and Express',
      image: 'https://via.placeholder.com/400x300.png?text=Project+3',
      url: '#'
    },
    {
      title: 'Project 4',
      description: 'A mobile app developed with React Native',
      image: 'https://via.placeholder.com/400x300.png?text=Project+4',
      url: '#'
    }
  ];
</script>

<section id="projects">
  <h2>Proyectos</h2>
  <div class="project-grid">
    {#each projects as project}
      <div class="project">
        <img src={project.image} alt={project.title} />
        <div class="overlay">
          <h3>{project.title}</h3>
          <p>{project.description}</p>
          <a href={project.url} class="btn" target="_blank" rel="noopener noreferrer">Ver proyecto</a>
        </div>
      </div>
    {/each}
  </div>
</section>

<style>
  section {
    padding: 2rem 0;
  }

  h2 {
    text-align: center;
    margin-bottom: 2rem;
    color: #333;
  }

  .project-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 0;
  }

  .project {
    position: relative;
    overflow: hidden;
  }

  .project img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    display: block;
    transition: transform 0.3s ease-in-out;
  }

  .overlay {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: rgba(0, 0, 0, 0.8);
    color: white;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 1rem;
    opacity: 0;
    transition: opacity 0.3s ease-in-out;
  }

  .project:hover .overlay {
    opacity: 1;
  }

  .project:hover img {
    transform: scale(1.1);
  }

  .overlay h3 {
    margin: 0 0 0.5rem 0;
    font-size: 1.5rem;
  }

  .overlay p {
    margin: 0 0 1rem 0;
    text-align: center;
  }

  .btn {
    background-color: #4CAF50;
    color: white;
    padding: 0.5rem 1rem;
    text-decoration: none;
    border-radius: 4px;
    transition: background-color 0.3s ease;
  }

  .btn:hover {
    background-color: #45a049;
  }

  :global(.dark) h2 {
    color: #ffffff;
  }

  :global(.dark) .overlay {
    background: rgba(255, 255, 255, 0.9);
    color: #333;
  }

  :global(.dark) .btn {
    background-color: #333;
    color: white;
  }

  :global(.dark) .btn:hover {
    background-color: #555;
  }
</style>