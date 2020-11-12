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
    padding: 0;
    /* height: 100vh; */
    /* background: darkorange; */
    background: radial-gradient(
          rgba(255, 255, 255, 0) 0,
          rgba(255, 255, 255, 0.15) 30%,
          rgba(255, 255, 255, 0.3) 32%,
          rgba(255, 255, 255, 0) 33%
        )
        0 0,
      radial-gradient(
          rgba(255, 255, 255, 0) 0,
          rgba(255, 255, 255, 0.1) 11%,
          rgba(255, 255, 255, 0.3) 13%,
          rgba(255, 255, 255, 0) 14%
        )
        0 0,
      radial-gradient(
          rgba(255, 255, 255, 0) 0,
          rgba(255, 255, 255, 0.2) 17%,
          rgba(255, 255, 255, 0.43) 19%,
          rgba(255, 255, 255, 0) 20%
        )
        0 110px,
      radial-gradient(
          rgba(255, 255, 255, 0) 0,
          rgba(255, 255, 255, 0.2) 11%,
          rgba(255, 255, 255, 0.4) 13%,
          rgba(255, 255, 255, 0) 14%
        ) -130px -170px,
      radial-gradient(
          rgba(255, 255, 255, 0) 0,
          rgba(255, 255, 255, 0.2) 11%,
          rgba(255, 255, 255, 0.4) 13%,
          rgba(255, 255, 255, 0) 14%
        )
        130px 370px,
      radial-gradient(
          rgba(255, 255, 255, 0) 0,
          rgba(255, 255, 255, 0.1) 11%,
          rgba(255, 255, 255, 0.2) 13%,
          rgba(255, 255, 255, 0) 14%
        )
        0 0,
      linear-gradient(
        45deg,
        #343702 0%,
        #184500 20%,
        #187546 30%,
        #006782 40%,
        #0b1284 50%,
        #760ea1 60%,
        #83096e 70%,
        #840b2a 80%,
        #b13e12 90%,
        #e27412 100%
      );
    background-size: 470px 470px, 970px 970px, 410px 410px, 610px 610px,
      530px 530px, 730px 730px, 100% 100%;
    background-color: #840b2a;
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
