<script>
    import { onMount } from 'svelte';
    import Welcome from './welcome.svelte';
    import Index from './index.svelte';

    let projects = [];

    onMount(async () => {
        const response = await fetch('src/routes/projects.json');
        projects = await response.json();
    });
</script>

<Welcome />
<Index projects={projects}/>