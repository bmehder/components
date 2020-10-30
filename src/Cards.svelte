<script>
  import { fly } from "svelte/transition";
</script>

<section in:fly={{ duration: 600, x: 1000, y: 0, opacity: 0.5 }}>
  <!-- <h3>3D Cards</h3> -->
  <div class="container">
    <div class="card">
      <div class="imgBx">
        <img src="/assets/card-1.jpg" alt="" />
      </div>
      <div class="content">
        <h2>Card One</h2>
        <p>
          Lorem, ipsum dolor sit amet consectetur adipisicing elit. Quisquam
          eveniet est esse ut dolor nostrum quam quod, quasi, quis accusantium
          veniam aperiam?
        </p>
      </div>
    </div>
    <div class="card">
      <div class="imgBx">
        <img src="/assets/card-2.jpg" alt="" />
      </div>
      <div class="content">
        <h2>Card Two</h2>
        <p>
          Lorem, ipsum dolor sit amet consectetur adipisicing elit. Quisquam
          eveniet est esse ut dolor nostrum quam quod, quasi, quis accusantium
          veniam aperiam?
        </p>
      </div>
    </div>
    <div class="card">
      <div class="imgBx">
        <img src="/assets/card-3.jpg" alt="" />
      </div>
      <div class="content">
        <h2>Card Three</h2>
        <p>
          Lorem, ipsum dolor sit amet consectetur adipisicing elit. Quisquam
          eveniet est esse ut dolor nostrum quam quod, quasi, quis accusantium
          veniam aperiam?
        </p>
      </div>
    </div>
  </div>
</section>

<style>
  @import url("https://fonts.googleapis.com/css2?family=Poppins&display=swap");

  * {
    font-family: "Poppins", sans-serif;
  }

  /* h3 {
    color: white;
  } */

  section {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    /* height: 100vh; */
    background: darkorange;
  }

  .container {
    position: relative;
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
    /* margin: 200px 0; */
  }

  .container .card {
    position: relative;
    max-width: 300px;
    height: 215px;
    background: #fff;
    margin: 30px 10px;
    padding: 20px 15px;
    display: flex;
    flex-direction: column;
    box-shadow: 0px 5px 20px rgba(0, 0, 0, 0.5);
    transition: 0.5s ease-in-out;
  }

  .container .card:hover {
    height: 420px;
  }

  .container .card .imgBx {
    position: relative;
    width: 260px;
    height: 260px;
    top: -60px;
    left: 5px;
    box-shadow: 0px 5px 20px rgba(0, 0, 0, 0.2);
    z-index: 1;
  }

  .container .card .imgBx img {
    max-width: 100%;
    border-radius: 4px;
  }

  .container .card .content {
    position: relative;
    margin-top: -140px;
    padding: 10px 15px;
    text-align: center;
    color: #111;
    visibility: hidden;
    opacity: 0;
    transition: 0.3s ease-in-out;
  }

  .container .card:hover .content {
    visibility: visible;
    opacity: 1;
    margin-top: -40px;
    transition-delay: 0.3s;
  }
</style>
