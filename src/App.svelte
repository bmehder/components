<script>
  // import Header from "./Header.svelte";
  import Logo from "./Logo.svelte";
  import Audio from "./Audio.svelte";
  import Video from "./Video.svelte";
  import Fetcher from "./Fetcher.svelte";
  import Hero from "./Hero.svelte";
  import Flex from "./Flex.svelte";
  import Neumorphism from "./Neumorphism.svelte";
  import Gooey from "./Gooey.svelte";
  import Hoverton from "./Hoverton.svelte";
  import Isometric from "./Isometric.svelte";
  import StarWars from "./StarWars.svelte";
  import Cards from "./Cards.svelte";
  import Gallery from "./gallery/Gallery.svelte";
  import Smoke from "./Smoke.svelte";
  import Typewriter from "./Typewriter.svelte";
  // import Footer from "./Footer.svelte";

  // Router
  const pages = [
    "audio",
    "video",
    "fetcher",
    "hero",
    "neumorphism",
    "flex",
    "gooey",
    "isometric",
    "star wars",
    "hover cards",
    "hoverton",
    "gallery",
    "smoke",
    "typewriter"
  ];
  let currentPage = pages[0];
  const switchPage = i => {
    currentPage = pages[i];
    console.log(currentPage);
  };
</script>

<!-- <Header /> -->
<main>
  <nav>
    <Logo />
    {#each pages as page, i}
      <a
        href={page}
        on:click|preventDefault={() => {
          switchPage(i);
        }}
        class:active={currentPage === page}>
        {page}
      </a>
    {/each}
  </nav>
  {#if currentPage === 'audio'}
    <Audio />
  {/if}

  {#if currentPage === 'video'}
    <Video />
  {/if}

  {#if currentPage === 'fetcher'}
    <Fetcher />
  {/if}

  {#if currentPage === 'hero'}
    <Hero />
  {/if}

  {#if currentPage === 'neumorphism'}
    <Neumorphism />
  {/if}

  {#if currentPage === 'flex'}
    <Flex />
  {/if}

  {#if currentPage === 'gooey'}
    <section style="background:black;padding:0;">
      <Gooey />
    </section>
  {/if}

  {#if currentPage === 'isometric'}
    <Isometric />
  {/if}

  {#if currentPage === 'star wars'}
    <StarWars />
  {/if}

  {#if currentPage === 'hover cards'}
    <Cards />
  {/if}

  {#if currentPage === 'hoverton'}
    <Hoverton />
  {/if}

  {#if currentPage === 'gallery'}
    <Gallery />
  {/if}

  {#if currentPage === 'smoke'}
    <Smoke />
  {/if}

  {#if currentPage === 'typewriter'}
    <Typewriter
      speed="100"
      phrase="So Long, and Thanks for All the Fish."
      audioNo="1" />
  {/if}
</main>

<style>
  main {
    display: flex;
    align-items: flex-start;
  }
  nav {
    display: flex;
    flex-direction: column;
    align-items: center;
    height: 100vh;
    width: 200px; /* 0 width - change this with JavaScript */
    background: #333;
    background-size: 50px 50px;
    overflow-x: hidden;
    padding: 0;
    transition: 0.4s;
  }
  nav a {
    padding: 0.8em 0;
    color: white;
    text-decoration: none;
    text-transform: capitalize;
  }
  a:hover,
  .active {
    color: darkorange;
    font-weight: bold;
  }
  @media (max-width: 600px) {
    nav {
      width: 0px;
    }
  }
</style>
