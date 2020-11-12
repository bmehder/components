<script>
  import { onMount } from "svelte";
  import { fade, fly } from "svelte/transition";
  import { elasticOut } from "svelte/easing";

  export let phrase =
    "const typing = () => typewriter = setInterval(typeChar, speed);";
  export let speed = 100;
  export let audioNo = 3;

  let typedChars = "";
  let index = 0;
  let typewriter;
  let finished;

  const typeChar = () => {
    if (index < phrase.length) {
      finished = false;
      playSFX();
      typedChars += phrase[index];
      index += 1;
    } else {
      clearInterval(typewriter);
      finished = true;
      index = 0;
    }
  };

  const typing = () => (typewriter = setInterval(typeChar, speed));

  const replay = () => {
    typedChars = "";
    typing();
  };

  const typingSFX = [
    "https://assets.codepen.io/504854/type_1.mp3",
    "https://assets.codepen.io/504854/type_2.mp3",
    "https://assets.codepen.io/504854/type_3.mp3"
  ];

  const playSFX = () => {
    let url = typingSFX[audioNo - 1];
    let keySFX = new Audio(url);

    keySFX.play();
  };

  onMount(() => typing());
</script>

<section>
  <h1 in:fly={{ y: -200, duration: 1000 }} out:fade>{typedChars}</h1>

  {#if finished}
    <button in:fly={{ y: -200, duration: 1000 }} out:fade on:click={replay}>
      &#8634;
    </button>
  {/if}
</section>

<style>
  section {
    position: relative;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    background: linear-gradient(#ffffff 50%, rgba(255, 255, 255, 0) 0) 0 0,
      radial-gradient(
          circle closest-side,
          #ffffff 53%,
          rgba(255, 255, 255, 0) 0
        )
        0 0,
      radial-gradient(
          circle closest-side,
          #ffffff 50%,
          rgba(255, 255, 255, 0) 0
        )
        55px 0 #48b;
    background-size: 110px 200px;
    background-repeat: repeat-x;
    color: white;
  }
  h1 {
    font-family: "Special Elite", cursive;
    font-size: 4em;
    line-height: 1.5em;
    width: 80%;
    text-shadow: 16px 32px 64px rgba(0, 0, 0, 1);
  }
  button {
    position: absolute;
    top: 5em;
    right: 1em;
    width: 60px;
    height: 60px;
    font-weight: bold;
    font-size: 2em;
    line-height: 1em;
    border-radius: 50%;
    background: darkorange;
    border: none;
    box-shadow: 16px 32px 64px rgba(0, 0, 0, 1),
      -16px -32px 64px rgba(255, 255, 255, 0.6);
  }
</style>
