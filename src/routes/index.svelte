<script context="module">
    import { client } from '$lib/graphql-client';
    import ProjectCard from '$lib/components/Project-Card.svelte';
    import { gql } from 'graphql-request';

    export const load = async () => {
        const query = gql`
            query geProjects {
                projects {
                    name
                    description
                    sourceCode
                }
            }
        `
        const { projects } = await client.request(query).catch((err) => console.error(err))
        console.log(projects)
        
        return {
            props: {
                projects,
            },
        }
    }
</script>

<script>
    export let projects
</script>

<h1>
    My Projects
</h1>

<div>
    {#each projects as { name, description, sourceCode } }
        <ProjectCard {name} {description} {sourceCode} />
    {/each}
</div>
  