<script lang="ts">
  import { onMount } from "svelte";

  const setVanta = async () => {
    await import(
      "https://cdn.jsdelivr.net/npm/vanta@latest/dist/vanta.globe.min.js"
    );
    console.log(window.VANTA);
    console.log(window.THREE);
    // @ts-ignore
    window.VANTA.GLOBE({
      el: "#vanta",
      mouseControls: true,
      touchControls: true,
      gyroControls: true,
      minHeight: 100.0,
      minWidth: 100.0,
      scale: 1.0,
      scaleMobile: 1.0,
      backgroundColor: 0xffffff,
    });
  };
</script>

<svelte:head>
  <script
    src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r121/three.min.js"
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
    min-height: 80vh;
    margin: 0 auto;
  }

  .text {
    position: absolute;
    top: 10rem;
    left: 50%;
    transform: translateX(-50%);
  }
  p {
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

    h1 {
      font-size: 5em;
    }

    .text {
      left: 20rem;
    }
  }
</style>
