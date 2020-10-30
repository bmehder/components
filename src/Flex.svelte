<script>
  import { fly } from "svelte/transition";
</script>

<section in:fly={{ delay: 250, duration: 600, x: 1000, y: 0, opacity: 0.5 }}>

  <!-- <h3>Flex Boxes</h3> -->
  <div>
    <article class="shadow">
      Lorem ipsum dolor, sit amet consectetur adipisicing elit. Explicabo
      assumenda aspernatur temporibus eius voluptatem labore consequatur sequi
      pariatur quod veritatis eum autem, consequuntur rem laboriosam aliquid,
      incidunt blanditiis?
    </article>

    <article class="shadow">
      Lorem ipsum dolor, sit amet consectetur adipisicing elit. Explicabo
      assumenda aspernatur temporibus eius voluptatem labore consequatur sequi
      pariatur quod veritatis eum autem, consequuntur rem laboriosam aliquid,
      incidunt blanditiis?
    </article>

    <article class="shadow">
      Lorem ipsum dolor, sit amet consectetur adipisicing elit. Explicabo
      assumenda aspernatur temporibus eius voluptatem labore consequatur sequi
      pariatur quod veritatis eum autem, consequuntur rem laboriosam aliquid,
      incidunt blanditiis?
    </article>
  </div>
</section>

<style>
  section {
    background: dodgerblue;
  }
  div {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-evenly;
    align-items: center;
    min-height: 80vh;
  }
  article {
    flex-basis: 250px;
    margin: 1em;
    padding: 2em;
    background: white;
    border: 1px solid #e1e1e1;
  }
</style>
