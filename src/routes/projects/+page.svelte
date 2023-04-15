<script>
    import { onMount } from 'svelte';
    import Index from './index.svelte';

    let projects = [];

    onMount(async () => {
        const response = await fetch('src/routes/projects.json');
        projects = await response.json();
    });
</script>

<Index projects={projects}/>

<style>
    @import '../main.css';
</style>