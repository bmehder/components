<script>
  import { fly } from "svelte/transition";
  export let image = "bg.jpg";
  export let source =
    "https://file-examples-com.github.io/uploads/2017/11/file_example_MP3_700KB.mp3";
</script>

<section id="audio" in:fly={{ duration: 600, x: 1000, y: 0, opacity: 0.5 }}>
  <!-- <h3>Audio Player</h3> -->
  <article>
    <figure>
      <img src="assets/{image}" alt="Background" />
    </figure>
    <!-- svelte-ignore a11y-media-has-caption -->
    <audio controls loop>
      <source src={source} type="audio/mp3" />
    </audio>
  </article>
</section>

<style>
  section {
    background: linear-gradient(45deg, darkorange, #fffde7);
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
  }
  article {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 350px;
    height: 350px;
    background: #f1f3f4;
  }
  figure {
    position: relative;
    width: 100%;
    height: 350px;
  }
  img {
    position: absolute;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
  audio {
    width: 100%;
    outline: none;
    display: block;
  }
</style>
