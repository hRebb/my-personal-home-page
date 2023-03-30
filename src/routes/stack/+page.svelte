<script>
    import Carousel from "./carousel.svelte";

    const images = [
        'src/routes/stack/img/bootstrap.png',
        'src/routes/stack/img/css-3.png',
        'src/routes/stack/img/git.png',
        'src/routes/stack/img/html.png',
        'src/routes/stack/img/icons8-node-js-48.png',
    ];
</script>

<Carousel {images} />