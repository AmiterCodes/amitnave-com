<script lang="ts">
  import { onMount } from "svelte";

  const setVanta = () => {
    // @ts-ignore

    window.VANTA.GLOBE({
      el: "#vanta",
      mouseControls: true,
      touchControls: true,
      gyroControls: true,
      minHeight: 700.0,
      minWidth: 600.0,
      scale: 1.0,
      scaleMobile: 1.0,
      backgroundColor: 0xffffff,
    });
  };
</script>

<svelte:head>
  <script
    src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r121/three.min.js"></script>
  <script
    src="https://cdn.jsdelivr.net/npm/vanta@latest/dist/vanta.globe.min.js"
    on:load={setVanta}></script>
</svelte:head>

<main id="vanta">
  <div class="text">
    <h1>Amit Nave</h1>
    <p>Web Developer or something</p>
  </div>
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  .text {
    position: absolute;
    top: 10rem;
    left: 10rem;
  }
  p {
    position: absolute;
    left: 5rem;
    margin-top: 0.1rem;
    font-size: 1rem;
  }
  h1 {
    margin: 0;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: bold;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
