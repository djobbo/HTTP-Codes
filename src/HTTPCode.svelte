<script>
  import { fade, fly } from "svelte/transition";
  export let code, title, desc, image;
  let clicked = false,
    hover = false;
</script>

<style>
  .code {
    display: flex;
    text-align: left;
    position: relative;
    cursor: pointer;
    background-color: #114;
    color: white;
    overflow: hidden;
    border: 1px solid black;
  }
  .code img {
    object-fit: cover;
    object-position: center;
    transition: 0.5s all ease;
    transform: scale(1.02);
  }

  .code img.clicked {
    opacity: 0.1;
  }

  .code:hover img {
    transform: scale(1.1);
  }

  .description {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    left: 0;
    padding: 1rem;
  }

  h3 {
    margin-top: 0;
    margin-bottom: 0.25rem;
  }

  p {
    margin: 0;
  }
</style>

<div
  class="code"
  on:click={e => (clicked = !clicked)}
  on:mouseenter={e => (hover = true)}
  on:mouseleave={e => (hover = false)}>
  <img src={image} alt={code} class:clicked={clicked || hover} />
  {#if clicked || hover}
    <div
      class="description"
      in:fly={{ y: 200, duration: 350 }}
      out:fade={{ duration: 250 }}>
      <h3>{title} ({code})</h3>
      <p>{desc}</p>
    </div>
  {/if}
</div>
