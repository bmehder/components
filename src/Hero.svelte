<script>
  export let media = "https://picsum.photos/1200/500";
  export let caption = "Just another hero image caption...";
</script>

<style>
  @import url("https://fonts.googleapis.com/css2?family=Source+Code+Pro:wght@700&display=swap");
  section {
    position: relative;
    margin: 0 0 0 150px;
    padding: 0;
  }
  img {
    display: block;
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
  div {
    position: absolute;
    width: 60%;
    top: 50%;
    left: 50%;
    margin-left: -75px;
    transform: translate(-50%, -50%);
    font-family: "Source Code Pro", monospace;
  }
  h3 {
    color: #fff;
    font-size: 4.5em;
    text-align: center;
    text-shadow: 2px 2px 3px rgba(0, 0, 0, 0.5);
  }
</style>

<section>
  <img src={media} alt="hero" />
  <div>
    <h3>{caption}</h3>
  </div>
</section>
