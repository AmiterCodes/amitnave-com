<script>
  import { onMount } from "svelte";
  import Section1 from "./Section1.svelte";

  import GLOBE from "vanta/dist/vanta.globe.min";

  onMount(() => {
    console.log(VANTA);
    GLOBE({
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
  });
</script>

<main id="vanta">
  <div class="text">
    <h1>עמית נווה</h1>
    <p>יזם, מפתח, הייטקיסט</p>
  </div>
  <img src="./assets/image.svg" alt="Person with PC" class="main-image" />
  <button class="button middle-button">הקורסים שלי</button>
</main>
<Section1 />

<style lang="scss">
  .middle-button {
    position: absolute;

    &:hover {
      transform: translate(-50%, -53%);
    }
    top: 90%;
    transform: translate(-50%, -50%);
    left: 50%;
  }
  .main-image {
    width: 50%;
    height: 50%;
    position: absolute;
    top: 70%;
    transform: translate(-50%, -50%);

    left: 50%;

    @media screen and (max-width: 600px) {
      width: 70%;
      height: 70%;
      top: 80%;
      left: 50%;
    }
  }

  :global(.button) {
    background: linear-gradient(147.88deg, #9e2ff5 9.82%, #4c6ec7 92.97%);
    border: none;
    padding: 1rem;
    cursor: pointer;
    border-radius: 100px;
    color: white;
  }

  :global(.title) {
    text-transform: uppercase;
    letter-spacing: 12px;
    font-size: 4rem;
    font-weight: 500;
  }
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

    line-height: 1;
    transform: translateX(-50%);

    margin: 0;
    text-transform: uppercase;
    font-size: 3em;
    font-weight: bold;
  }
  h1 {
    margin-bottom: 0.1rem;
  }
  p {
    margin-top: 0.1rem;
    font-size: 1rem;
  }

  #vanta {
    height: 100vh;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }

    h1 {
      font-size: 2em;
    }

    .text {
      left: 20rem;
    }
  }
</style>
