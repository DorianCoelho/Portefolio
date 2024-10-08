<script lang="ts">
  let name = '';
  let email = '';
  let message = '';

  function handleSubmit() {
    // Here you would typically handle form submission
    console.log('Form submitted', { name, email, message });
    // Reset form fields
    name = '';
    email = '';
    message = '';
  }
</script>

<section id="contact">
  <h2>Contact Me</h2>
  <form on:submit|preventDefault={handleSubmit}>
    <div class="form-group">
      <label for="name">Name</label>
      <input type="text" id="name" bind:value={name} required>
    </div>
    <div class="form-group">
      <label for="email">Email</label>
      <input type="email" id="email" bind:value={email} required>
    </div>
    <div class="form-group">
      <label for="message">Message</label>
      <textarea id="message" bind:value={message} required></textarea>
    </div>
    <button type="submit">Send Message</button>
  </form>
</section>

<style>
  section {
    padding: 2rem;
    background-color: #f9f9f9;
    border-radius: 8px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    margin: 2rem 0;
  }

  h2 {
    text-align: center;
    margin-bottom: 1.5rem;
    color: #333;
  }

  form {
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
    max-width: 500px;
    margin: 0 auto;
  }

  .form-group {
    display: flex;
    flex-direction: column;
  }

  label {
    margin-bottom: 0.5rem;
    font-weight: bold;
    color: #555;
  }

  input, textarea {
    padding: 0.75rem;
    border: 1px solid #ddd;
    border-radius: 4px;
    font-size: 1rem;
    transition: border-color 0.3s ease;
  }

  input:focus, textarea:focus {
    outline: none;
    border-color: #4CAF50;
    box-shadow: 0 0 0 2px rgba(76, 175, 80, 0.2);
  }

  textarea {
    min-height: 150px;
    resize: vertical;
  }

  button {
    align-self: flex-start;
    padding: 0.75rem 1.5rem;
    background-color: #4CAF50;
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    font-size: 1rem;
    transition: background-color 0.3s ease;
  }

  button:hover {
    background-color: #45a049;
  }

  :global(.dark) section {
    background-color: #2a2a2a;
  }

  :global(.dark) h2 {
    color: #ffffff;
  }

  :global(.dark) label {
    color: #cccccc;
  }

  :global(.dark) input, :global(.dark) textarea {
    background-color: #3a3a3a;
    border-color: #555;
    color: #ffffff;
  }

  :global(.dark) input:focus, :global(.dark) textarea:focus {
    border-color: #4CAF50;
    box-shadow: 0 0 0 2px rgba(76, 175, 80, 0.3);
  }

  :global(.dark) button {
    background-color: #4CAF50;
  }

  :global(.dark) button:hover {
    background-color: #45a049;
  }
</style>