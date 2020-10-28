<script>
  document.querySelector("body").addEventListener("mousemove", eyeball);

  function eyeball() {
    let eye = document.querySelectorAll(".eye");
    eye.forEach(eye => {
      let x = eye.getBoundingClientRect().left + eye.clientWidth / 2;
      // console.log(x);
      let y = eye.getBoundingClientRect().top + eye.clientHeight / 2;
      let radian = Math.atan2(event.pageX - x, event.pageY - y);
      let rot = radian * (180 / Math.PI) * -1 + 270;
      eye.style.transform = "rotate(" + rot + "deg)";
    });
  }
</script>

<style>
  h3 {
    color: white;
  }
  section {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    background: #333;
    overflow: hidden;
  }

  .face {
    position: relative;
    width: 300px;
    height: 300px;
    border-radius: 50%;
    background: #ffcd00;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .face::before {
    content: "";
    position: absolute;
    top: 180px;
    width: 150px;
    height: 70px;
    background: #b57700;
    border-bottom-left-radius: 70px;
    border-bottom-right-radius: 70px;
    transition: 0.5s;
  }

  .face:hover::before {
    top: 210px;
    width: 150px;
    height: 20px;
    background: #b57700;
    border-bottom-left-radius: 0px;
    border-bottom-right-radius: 0px;
    transition: 0.5s;
  }

  .eyes {
    position: relative;
    top: -40px;
    display: flex;
  }

  .eyes .eye {
    position: relative;
    width: 80px;
    height: 80px;
    display: block;
    background: #fff;
    margin: 0 15px;
    border-radius: 50%;
  }

  .eyes .eye::before {
    content: "";
    position: absolute;
    top: 50%;
    left: 25px;
    transform: translate(-50%, -50%);
    width: 40px;
    height: 40px;
    background: #333;
    border-radius: 50%;
  }
</style>

<section>
  <h3>
    Eyes
    <br />
    <small>(Under Construction)</small>
  </h3>
  <div class="face">
    <div class="eyes">
      <div class="eye" />
      <div class="eye" />
    </div>
  </div>
</section>
