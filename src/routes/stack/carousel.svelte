<script lang="ts">
    import {onMount} from 'svelte';
    import {onCleanup} from 'svelte';
    import {onInterval} from 'svelte';
    import {setContext} from 'svelte';
    import {getContext} from 'svelte';

    const INTERVAL_DELAY = 3000;

    interface Props {
        images: string[];
    }

    type Context = number;

    export let images: Props["images"] = [];

    const [current, setCurrent] = setContext<Context>('current', 0);

    let interval: () => void;

    onMount(() => {
        interval = onInterval(() => {
            setCurrent((contextImages) => (contextImages + 1) % images.length)
        }, INTERVAL_DELAY); 
    });

    onCleanup(() => {
        interval();
    });

    function next() {
        setCurrent((contextImages) => (contextImages + 1) % images.length)
    }

    function previous() {
        setCurrent((contextImages) => (contextImages - 1) % images.length)
    }
</script>

<div class="carousel">
    <button on:click={previous}>Previous</button>
    <img src={images[current]} alt="carousel image">
    <button on:click={next}>Next</button>
</div>

<style>
    @import "./carousel.css";
</style>