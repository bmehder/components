<script>
  export let text = "SMOKE";
</script>

<style>
  @import url("https://fonts.googleapis.com/css2?family=Poppins:wght@200;300;400;500;600;700;800;900&display=swap");
  section {
    font-family: "Poppins", sans-serif;
    position: relative;
    width: 100%;
    background: #000;
    display: flex;
    justify-content: center;
    align-items: center;
    overflow: hidden;
  }
  section h2 {
    position: relative;
    font-size: 6em;
    color: #fff;
    text-align: center;
    z-index: 10000;
    mix-blend-mode: overlay;
  }
  section video {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
</style>

<section>
  <h2>{text}</h2>
  <video src="/assets/smoke.mp4" muted loop autoplay type="mp4" />
</section>
