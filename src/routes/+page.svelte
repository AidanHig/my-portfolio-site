<script>
  import FandF from '$lib/assets/FandF.png';
  import Fireball from '$lib/assets/Fireball.png';
  import HappyDriver from '$lib/assets/godot.png';

  const featuredProjects = [
    {
      title: "Body and Soul",
      description: "A 2v2 ability based MOBA. Fight as a monk or a spirit tethered together and select upgrades to defeat your opponents!",
      videoUrl: "https://www.youtube.com/embed/qs-WRy48GvI",
      links: [
        { label: "Download on itch.io", url: "https://bighig.itch.io/body-and-soul" }
      ]
    },
    {
      title: "Galactic Coffee Shop",
      description: "Grow your coffee enterprise from a single stand to an empire stretching across the stars! Bring the gift of coffee to the stars!",
      videoUrl: "https://www.youtube.com/embed/1F3B8xAAKe8",
      links: [
        { label: "Steam Demo", url: "https://store.steampowered.com/app/3692320/Galactic_Coffee_Shop/" }
      ]
    }
  ];

  const prototypes = [
    { title: "Fortify and Funnel", description: "Build barricades to keep the evil skeletons away from your base (Unity)", link: "https://bighig.itch.io/fortify-and-funnel", image: FandF },
    { title: "Fireball", description: "Cast spells by drawing runes and yelling into your mic (UE5)", link: "https://illuminati-cow.itch.io/fireball", image: Fireball },
    { title: "Happy Driver", description: "Change the radio station and music volume to keep your driver happy (Godot)", link: "https://bighig.itch.io/happy-driver", image: HappyDriver }
  ];
</script>

<svelte:head>
  <title>Aidan Higgins – Game Designer</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com">
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
</svelte:head>

<main class="container">
  <header class="header">
    <h1 class="main-title">Aidan Higgins</h1>
    <p class="subtitle">Game Design · System Design · Fullstack Engineer</p>
  </header>

  <section class="featured-section">
    <h2 class="section-title">Featured Projects</h2>
    <div class="featured-grid">
      {#each featuredProjects as project}
        <div class="featured-card">
          <h3 class="project-title">{project.title}</h3>
          <p class="project-description">{project.description}</p>
          {#if project.videoUrl}
            <div class="video-container">
              <iframe src={project.videoUrl} frameborder="0" allowfullscreen></iframe>
            </div>
          {/if}
          <div class="project-links">
            {#each project.links as link}
              <a class="project-link" href={link.url} target="_blank">{link.label}</a>
            {/each}
          </div>
        </div>
      {/each}
    </div>
  </section>

  <section class="prototypes-section">
    <h2 class="section-title">Prototypes</h2>
    <div class="prototypes-grid">
      {#each prototypes as proto}
        <div class="prototype-card">
          {#if proto.image}
            <img src={proto.image} alt={proto.title} class="prototype-image" />
          {/if}
          <h3 class="prototype-title">{proto.title}</h3>
          <p class="prototype-description">{proto.description}</p>
          {#if proto.link}
            <a href={proto.link} class="prototype-link" target="_blank">View on itch.io</a>
          {/if}
        </div>
      {/each}
    </div>
  </section>

  <footer class="footer">
    <p>© 2025 Aidan Higgins · 
      <a href="mailto:aidan.x.higgins@gmail.com" class="footer-link">Email Me</a> · 
      <a href="https://linkedin.com/in/aidan-higgins-71a3aa230/" target="_blank" class="footer-link">LinkedIn</a> · 
      <a href="https://bighig.itch.io" target="_blank" class="footer-link">itch.io</a>
    </p>
  </footer>
</main>

<style>
  :global(body) {
    background: linear-gradient(135deg, #0f0f23 0%, #1a1a2e 100%);
    color: #e2e8f0;
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
    line-height: 1.6;
    margin: 0;
    padding: 0;
    min-height: 100vh;
  }

  .container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 2rem;
  }

  /* Header Styles */
  .header {
    text-align: center;
    margin-bottom: 4rem;
    padding: 2rem 0;
  }

  .main-title {
    font-size: 3.5rem;
    font-weight: 700;
    background: linear-gradient(135deg, #60a5fa 0%, #3b82f6 50%, #1d4ed8 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 0.5rem;
    letter-spacing: -0.02em;
  }

  .subtitle {
    font-size: 1.25rem;
    color: #94a3b8;
    font-weight: 400;
    letter-spacing: 0.025em;
  }

  /* Section Titles */
  .section-title {
    font-size: 2rem;
    font-weight: 600;
    margin-bottom: 2rem;
    color: #f1f5f9;
    letter-spacing: -0.01em;
  }

  /* Featured Projects */
  .featured-section {
    margin-bottom: 4rem;
  }

  .featured-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(500px, 1fr));
    gap: 2rem;
  }

  .featured-card {
    background: rgba(30, 41, 59, 0.9);
    border: 1px solid rgba(71, 85, 105, 0.5);
    border-radius: 20px;
    padding: 2.5rem;
    backdrop-filter: blur(15px);
    transition: all 0.3s ease;
    box-shadow: 0 8px 32px rgba(0, 0, 0, 0.2);
  }

  .featured-card:hover {
    border-color: rgba(96, 165, 250, 0.6);
    transform: translateY(-4px);
    box-shadow: 0 25px 50px rgba(0, 0, 0, 0.3);
  }

  .project-title {
    font-size: 1.5rem;
    font-weight: 600;
    margin-bottom: 1rem;
    color: #f8fafc;
  }

  .project-description {
    color: #cbd5e1;
    margin-bottom: 1.5rem;
    font-size: 1rem;
    line-height: 1.7;
  }

  .video-container {
    position: relative;
    width: 100%;
    padding-top: 56.25%;
    margin-bottom: 1.5rem;
    border-radius: 12px;
    overflow: hidden;
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.3);
  }

  .video-container iframe {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    border: none;
  }

  .project-links {
    display: flex;
    gap: 1rem;
    flex-wrap: wrap;
  }

  .project-link {
    color: #60a5fa;
    text-decoration: none;
    font-weight: 500;
    padding: 0.5rem 1rem;
    border: 1px solid rgba(96, 165, 250, 0.3);
    border-radius: 8px;
    transition: all 0.2s ease;
    font-size: 0.9rem;
  }

  .project-link:hover {
    background: rgba(96, 165, 250, 0.1);
    border-color: rgba(96, 165, 250, 0.6);
    transform: translateY(-1px);
  }

  /* Prototypes */
  .prototypes-section {
    margin-bottom: 4rem;
  }

  .prototypes-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 1.5rem;
  }

  .prototype-card {
    background: rgba(30, 41, 59, 0.7);
    border: 1px solid rgba(71, 85, 105, 0.4);
    border-radius: 16px;
    padding: 1.5rem;
    backdrop-filter: blur(10px);
    transition: all 0.3s ease;
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
  }

  .prototype-card:hover {
    border-color: rgba(96, 165, 250, 0.4);
    transform: translateY(-2px);
    box-shadow: 0 15px 25px rgba(0, 0, 0, 0.15);
  }

  .prototype-image {
    width: 100%;
    height: 200px;
    object-fit: cover;
    border-radius: 12px;
    margin-bottom: 1rem;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
  }

  .prototype-title {
    font-size: 1.25rem;
    font-weight: 600;
    margin-bottom: 0.5rem;
    color: #f1f5f9;
  }

  .prototype-description {
    color: #94a3b8;
    font-size: 0.9rem;
    margin-bottom: 1rem;
    line-height: 1.6;
  }

  .prototype-link {
    color: #60a5fa;
    text-decoration: none;
    font-weight: 500;
    font-size: 0.875rem;
    transition: color 0.2s ease;
  }

  .prototype-link:hover {
    color: #93c5fd;
  }

  /* Footer */
  .footer {
    margin-top: 4rem;
    padding: 2rem 0;
    text-align: center;
    border-top: 1px solid rgba(71, 85, 105, 0.3);
  }

  .footer p {
    color: #64748b;
    font-size: 0.9rem;
  }

  .footer-link {
    color: #60a5fa;
    text-decoration: none;
    transition: color 0.2s ease;
  }

  .footer-link:hover {
    color: #93c5fd;
  }

  /* Responsive Design */
  @media (max-width: 768px) {
    .container {
      padding: 1rem;
    }

    .main-title {
      font-size: 2.5rem;
    }

    .subtitle {
      font-size: 1.1rem;
    }

    .featured-grid {
      grid-template-columns: 1fr;
    }

    .featured-card,
    .prototype-card {
      padding: 1.5rem;
    }

    .section-title {
      font-size: 1.75rem;
    }
  }

  @media (max-width: 480px) {
    .main-title {
      font-size: 2rem;
    }

    .prototypes-grid {
      grid-template-columns: 1fr;
    }
  }
</style>