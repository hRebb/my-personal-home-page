<script>
    import {onMount} from "svelte";
    import Timeline from "$lib/components/timeline.svelte";

    let events = [];

    onMount(async() => {
        const datas = await fetch('src/routes/events.json');
        events = await datas.json();
    })
</script>

<h1 class="title">
    My Career Timeline
</h1>

<template>
    <Timeline {events} />
</template>

<style>
    @import './career.css';
</style>