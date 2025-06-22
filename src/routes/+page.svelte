

<!-- src/routes/+page.svelte -->
<script>
  import FandF from '$lib/assets/FandF.png';
  import Fireball from '$lib/assets/Fireball.png';

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
      title: "Galacic Coffee Shop",
      description: "Grow your coffee enterprise from a single stand to an empire stretching across the stars! Go from grinding beans to hiring employees to buying buildings to consuming planets! Bring the gift of coffee to the stars!",
      videoUrl: "https://www.youtube.com/embed/nWmT8oGho5c",
      links: [
        { label: "Steam demo", url: "https://store.steampowered.com/app/3692320/Galactic_Coffee_Shop/" }
      ]
    }
  ];

  const prototypes = [
    { title: "Fortify and Funnel", description: "Build barricades to keep the evil skeletons away from your base!", link: "https://bighig.itch.io/fortify-and-funnel", image: FandF },
    { title: "Fireball", description: "Cast spells by drawing runes and speaking (yelling) into your mic at the same time.", link: "https://illuminati-cow.itch.io/fireball", image: Fireball },
    // { title: "Tradio", description: " ", link: "https://illuminati-cow.itch.io/tradio", image: ProceduralDungeonImg }
  ];
</script>

<svelte:head>
  <title>Aidan Higgins – Game Designer</title>
</svelte:head>

<main class="px-6 py-12 max-w-4xl mx-auto text-white">
  <header class="text-center">
    <h1 class="text-4xl font-bold">Aidan Higgins</h1>
    <p class="text-lg text-gray-400">Game Design · System Design · Fullstack Engineer</p>
  </header>

  <section class="mt-16">
    <h2 class="text-2xl font-semibold mb-6">Featured Projects</h2>
    {#each featuredProjects as project}
      <div class="mb-12">
        <h3 class="text-xl font-bold">{project.title}</h3>
        <p class="text-gray-300 mb-2">{project.description}</p>
        {#if project.videoUrl}
          <div class="aspect-video mb-2">
            <iframe src={project.videoUrl} class="w-full h-full" frameborder="0" allowfullscreen></iframe>
          </div>
        {/if}
        <div class="flex gap-4 flex-wrap">
          {#each project.links as link}
            <a class="text-sky-400 hover:underline" href={link.url} target="_blank">{link.label}</a>
          {/each}
        </div>
      </div>
    {/each}
  </section>

  <section class="mt-16">
    <h2 class="text-2xl font-semibold mb-6">Prototypes</h2>
    <div class="grid grid-cols-1 sm:grid-cols-2 gap-6">
      {#each prototypes as proto}
        <div class="bg-gray-800 p-4 rounded">
          {#if proto.image}
            <img src={proto.image} alt={proto.title} class="rounded mb-3" />
          {/if}
          <h3 class="text-lg font-semibold">{proto.title}</h3>
          <p class="text-gray-400">{proto.description}</p>
          {#if proto.link}
            <p class="mt-2"><a href={proto.link} class="text-sky-400 hover:underline" target="_blank">View on itch.io</a></p>
          {/if}
        </div>
      {/each}
    </div>
  </section>

  <footer class="mt-20 text-center text-sm text-gray-500">
    <p>© 2025 Aidan Higgins · <a href="mailto:your@email.com" class="hover:underline">Email Me</a> · <a href="https://linkedin.com/in/yourprofile" target="_blank" class="hover:underline">LinkedIn</a> · <a href="https://your.itch.io" target="_blank" class="hover:underline">itch.io</a></p>
  </footer>
</main>

<style>
  body {
    background-color: #111;
  }
</style>
