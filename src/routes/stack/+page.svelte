<script>
    import {onMount} from "svelte";
    import Carousel from "./carousel.svelte";

    const images = [
        'src/routes/stack/img/bootstrap-logo.png',
        'src/routes/stack/img/css-3.png',
        'src/routes/stack/img/git.png',
        'src/routes/stack/img/html.png',
        'src/routes/stack/img/icons8-node-js-48.png',
    ];

    let currentIndex = 0;

    function onNext() {
        currentIndex = (currentIndex + 1) % images.length;
    }

    function onPrev() {
        currentIndex = currentIndex === 0 ? images.length - 1 : currentIndex - 1;
    }

    onMount(() => {
        const intervalId = setInterval(() => {
            onNext();
        }, 3000);

        return () => {
            clearInterval(intervalId);
        };
    });
</script>

<div class="container">
    <Carousel images={images} currentIndex={currentIndex} />
    <div class="buttons">
      <button on:click={onPrev}>Previous</button>
      <button on:click={onNext}>Next</button>
    </div>
  </div>
  
  <style>
    .container {
      display: flex;
      flex-direction: column;
      align-items: center;
    }
  
    .buttons {
      display: flex;
      justify-content: center;
      margin-top: 1rem;
    }
  </style>