<script>
  import { images } from "./gallery-components/imageData.js";
  import Slide from "./gallery-components/Slide.svelte";
  import Caption from "./gallery-components/Caption.svelte";
  import Thumbnail from "./gallery-components/Thumbnail.svelte";

  /* IMAGE TO SHOW */
  let imageShowingIndex = 0;
  $: image = images[imageShowingIndex];
  $: console.log(imageShowingIndex);

  const nextSlide = () => {
    if (imageShowingIndex === images.length - 1) {
      imageShowingIndex = 0;
    } else {
      imageShowingIndex += 1;
    }
  };

  const prevSlide = () => {
    if (imageShowingIndex === 0) {
      imageShowingIndex = images.length - 1;
    } else {
      imageShowingIndex -= 1;
    }
  };

  const goToSlide = number => (imageShowingIndex = number);
</script>

<style>
  @import url("https://fonts.googleapis.com/css2?family=Josefin+Sans:wght@500&display=swap");

  * {
    box-sizing: border-box;
    font-family: "Josefin Sans", sans-serif;
  }

  main {
    width: 50vw;
    display: flex;
    flex-direction: column;
    align-items: center;
    margin: 0;
    background-color: #222;
    box-shadow: 10px 10px 30px rgba(0, 0, 0, 0.3);
  }
  section {
    display: flex;
    justify-content: center;
    align-items: center;
  }
  /* Position the image container (needed to position the left and right arrows) */
  .container {
    position: relative;
  }

  .thumbnails-row {
    width: 100%;
    display: flex;
    align-self: flex-end;
  }
</style>

<section>
  <main>

    <!-- image gallery -->
    <div class="container">
      <Slide
        image={image.imgurl}
        altTag={image.name}
        attr={image.attribution}
        slideNo={image.id + 1}
        totalSlides={images.length} />
    </div>

    <!-- Image text -->
    <Caption
      caption={image.name}
      on:prevClick={prevSlide}
      on:nextClick={nextSlide} />

    <!-- Thumbnail images -->
    <div class="thumbnails-row">
      {#each images as { id, imgurl, name }}
        <Thumbnail
          thumbImg={imgurl}
          altTag={name}
          {id}
          selected={imageShowingIndex === id}
          on:click={() => goToSlide(id)} />
      {/each}
    </div>

  </main>
</section>
