<script lang="ts">
  // You can replace this URL with your actual photo URL
  const photoUrl = "https://via.placeholder.com/150";
</script>

<section id="about">
  <div class="about-content">
    <div class="photo-container">
      <img src={photoUrl} alt="Profile photo" class="profile-photo" />
    </div>
    <div class="text-content">
      <h2>About Me</h2>
      <p>
        Hello! I'm a fullstack developer passionate about creating beautiful and functional web applications.
        With expertise in both frontend and backend technologies, I strive to deliver high-quality, scalable solutions.
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