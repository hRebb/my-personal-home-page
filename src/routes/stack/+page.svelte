<script>
    import Carousel from "./carousel.svelte";

    const images = [
        'src/routes/stack/img/bootstrap-logo.png',
        'src/routes/stack/img/css3-vector.png',
        'src/routes/stack/img/html5-logo-vector-01.png',
        'src/routes/stack/img/mysql.png',
        'src/routes/stack/img/python.svg',
        'src/routes/stack/img/react-logo.png',
        'src/routes/stack/img/sass.svg',
        'src/routes/stack/img/svelte.svg',
        'src/routes/stack/img/typescript.svg',
    ];
</script>

<div class="container">
    <Carousel images={images}/>
</div>
  
<style>
    .container {
      display: flex;
      flex-direction: column;
      align-items: center;
    }
</style>