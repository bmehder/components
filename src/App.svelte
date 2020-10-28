<script>
  // import Header from "./Header.svelte";
  import Logo from "./Logo.svelte";
  import Audio from "./Audio.svelte";
  import Video from "./Video.svelte";
  import Fetcher from "./Fetcher.svelte";
  import Flex from "./Flex.svelte";
  import Neumorphism from "./Neumorphism.svelte";
  import Gooey from "./Gooey.svelte";
  import Hoverton from "./Hoverton.svelte";
  import Cards from "./Cards.svelte";
  import Gallery from "./Gallery.svelte";
  import Smoke from "./Smoke.svelte";
  // import Footer from "./Footer.svelte";

  // Router
  const pages = [
    "audio",
    "video",
    "fetcher",
    "neumorphism",
    "flex",
    "gooey",
    "cards",
    "hoverton",
    "gallery",
    "smoke"
  ];
  let currentPage = pages[0];
  const switchPage = i => {
    currentPage = pages[i];
    console.log(currentPage);
  };
</script>

<style>
  nav {
    display: flex;
    flex-direction: column;
    align-items: center;
    height: 100%;
    width: 150px; /* 0 width - change this with JavaScript */
    position: absolute;
    z-index: 1;
    top: 0;
    left: 0;
    background: #333;
    background-size: 50px 50px;
    overflow-x: hidden;
    padding: 0;
    transition: 0.4s;
  }
  nav a {
    padding: 1em 0;
    color: white;
    text-decoration: none;
    text-transform: capitalize;
  }
  a:hover,
  .active {
    color: darkorange;
    font-weight: bold;
  }
  @media (max-width: 400px) {
    nav {
      width: 0px;
    }
  }
</style>

<!-- <Header /> -->
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

{#if currentPage === 'cards'}
  <Cards />
{/if}

{#if currentPage === 'hoverton'}
  <Hoverton />
{/if}

{#if currentPage === 'gallery'}
  ncjsanckj
  <Gallery />
{/if}

{#if currentPage === 'smoke'}
  <Smoke />
{/if}

<!-- <Footer /> -->
