<script lang="ts">
    export let images: string[];
    export let currentIndex: number;
</script>

<div class="carousel">
    <div class="slides" style="transform: translateX(-${currentIndex * 100}%)">
        {#each images as image }
            <img src={image} alt="" />
        {/each}
    </div>
</div>

<style>
    @import './carousel.css';
</style>