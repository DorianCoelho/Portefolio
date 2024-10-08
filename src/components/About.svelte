<script lang="ts">
  // You can replace this URL with your actual photo URL
  const photoUrl = "https://media.licdn.com/dms/image/v2/C5603AQGAir7_7sAWQw/profile-displayphoto-shrink_800_800/profile-displayphoto-shrink_800_800/0/1633426424493?e=1733961600&v=beta&t=P469QUObjPk_E_tcM3GjaqrGQhRQdjoOVC9OdHYnkK8";
</script>

<section id="about">
  <div class="about-content">
    <div class="photo-container">
      <img src={photoUrl} alt="Profile photo" class="profile-photo" />
    </div>
    <div class="text-content">
      <h2>Acerca de min</h2>
      <p>
       Soy desarrollador fullstack con más de 5 años de experiencia en .NET y desarrollo de APIs REST. Trabajo con tecnologías de backend como Entity Framework, MVC y Postgres, y de frontend como JavaScript, HTML, CSS y Razor. Me enfoco en crear soluciones web dinámicas y eficientes, con un compromiso constante por el aprendizaje y la mejora continua.
      </p>
    </div>
  </div>
</section>

<style>
  .about-content {
    display: flex;
    align-items: center;
    gap: 2rem;
  }

  .photo-container {
    flex-shrink: 0;
  }

  .profile-photo {
    width: 150px;
    height: 150px;
    border-radius: 50%;
    object-fit: cover;
    border: 4px solid #4CAF50;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  }

  .text-content {
    flex-grow: 1;
  }

  h2 {
    margin-top: 0;
  }

  @media (max-width: 768px) {
    .about-content {
      flex-direction: column;
      text-align: center;
    }
  }

  :global(.dark) .profile-photo {
    border-color: #45a049;
  }
</style>