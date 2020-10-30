<article>
  <div class="wrapper">
    <div class="scroll-text">
      <h1>STAR WARS</h1>
      <h2>Scrolling Text Effect</h2>
      <p>
        Lorem ipsum dolor sit amet consectetur, adipisicing elit. Ad maiores aut
        cupiditate unde ipsam ut fugit deleniti non autem, ab, tempore ratione
        quo, nihil delectus sequi incidunt voluptates quis. Expedita!
      </p>
      <p>
        Lorem ipsum dolor sit amet consectetur, adipisicing elit. Ad maiores aut
        cupiditate unde ipsam ut fugit deleniti non autem, ab, tempore ratione
        quo, nihil delectus sequi incidunt voluptates quis. Expedita!
      </p>
      <p>
        Lorem ipsum dolor sit amet consectetur, adipisicing elit. Ad maiores aut
        cupiditate unde ipsam ut fugit deleniti non autem, ab, tempore ratione
        quo, nihil delectus sequi incidunt voluptates quis. Expedita!
      </p>
      <p>
        Lorem ipsum dolor sit amet consectetur, adipisicing elit. Ad maiores aut
        cupiditate unde ipsam ut fugit deleniti non autem, ab, tempore ratione
        quo, nihil delectus sequi incidunt voluptates quis. Expedita!
      </p>
      <p>
        Lorem ipsum dolor sit amet consectetur, adipisicing elit. Ad maiores aut
        cupiditate unde ipsam ut fugit deleniti non autem, ab, tempore ratione
        quo, nihil delectus sequi incidunt voluptates quis. Expedita!
      </p>
    </div>
  </div>
</article>

<style>
  @import url("https://fonts.googleapis.com/css2?family=Roboto:wght@500;700&display=swap");

  article {
    background: rgb(20, 20, 20);
    overflow: hidden;
    font-family: "Roboto";
    /* push down the the wrapper by half the page */
    margin: 10% 0 0 0;
    /* position: relative; */
  }
  article::after {
    content: "";
    position: fixed;
    top: 0;
    width: 100%;
    height: 50%;
    /* background to fade out the text as it goes up */
    background: linear-gradient(
      180deg,
      rgba(20, 20, 20, 1) 40%,
      rgba(20, 20, 20, 0) 100%
    );
  }
  .wrapper {
    display: flex;
    height: 100%;
    width: 60%;
    margin: 0 auto;
    /* perspective gives us a 3d space within the element to work with*/
    /* perspective also has the effect of pushing the content "down" */
    perspective: 450px;
  }
  .scroll-text {
    margin: 0;
    padding: 0;
    color: #ffc909;
    /* font-size: 2vw; */
    line-height: 1.5em;
    font-weight: bold;
    text-align: justify;
    position: relative;
    animation: scroll 200s linear infinite;
  }
  h1,
  h2 {
    margin: 1em auto;
    text-align: center;
  }
  p {
    margin: 1em 0;
  }

  @keyframes scroll {
    from {
      top: 0;
      transform: translateZ(0) rotateX(20deg);
    }
    to {
      top: -7500px;
      transform: translateZ(-2500px) rotateX(21deg);
    }
  }
</style>
