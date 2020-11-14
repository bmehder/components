<script>
  import { fly } from "svelte/transition";
</script>

<section in:fly={{ duration: 600, x: 1000, y: 0, opacity: 0.5 }}>
  <h2 data-text="Glowing">Glowing</h2>
</section>

<style>
  section {
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    background: radial-gradient(#111, #000);
    font-family: "Nunito", sans-serif;
  }

  h2 {
    position: relative;
    font-size: 10em;
    text-transform: uppercase;
    color: white;
    background: linear-gradient(
      to bottom,
      #222 0%,
      #222 50%,
      #111 50%,
      #111 100%
    );
    background-clip: text;
    -webkit-background-clip: text;
  }

  h2::before {
    content: attr(data-text);
    position: absolute;
    top: 4px;
    left: 4px;
    /* z-index: -1; */
    background: linear-gradient(45deg, #ff0, #0f0, #f00, #00f, #0f0);
    background-clip: text;
    -webkit-background-clip: text;
    color: transparent;
  }

  h2::after {
    content: attr(data-text);
    position: absolute;
    top: 30px;
    left: 20px;
    /* z-index: -2; */
    background: linear-gradient(45deg, #ff0, #0f0, #f00, #00f, #0f0);
    background-clip: text;
    -webkit-background-clip: text;
    color: transparent;
    filter: blur(20px);
  }
</style>
