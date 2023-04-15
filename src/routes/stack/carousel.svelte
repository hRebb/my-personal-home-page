<script lang="ts">
  export let images: string[] = [];
  let index = 0;

  function nextImage() {
    index = (index + 1) % images.length;
  }

  function previousImage() {
    index = (index - 1 + images.length) % images.length;
  }
</script>


<h1 class="title">
  My Stack
</h1>


<div>
  <button on:click={previousImage}>Previous</button>
  <img src={images[index]} alt='' />
  <button on:click={nextImage}>Next</button>
</div>

<style>
    @import '../main.css';
    @import './carousel.css';
</style>