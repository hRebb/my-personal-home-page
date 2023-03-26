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

    let visibleCards = 1;
    const maxVisibleCards = 3;

    let nextBtn;
    let returnBtn;

    function scrollRight() {
        if (visibleCards < projects.length) {
            const currentCard = document.querySelector(`.project-card:nth-child(${visibleCards})`)
            currentCard.classList.add("shifted");
            visibleCards++;
        }
    }

    function scrollLeft() {
        if (visibleCards > 1) {
            visibleCards--;
            const currentCard = document.querySelector(`.project-card:nth-child(${visibleCards + 2})`);
            currentCard.classList.remove("shifted");
        }
    }
</script>

<h1 class="title">
    My Projects
</h1>

<div class="project-container">
    {#each projects as { name, description, sourceCode }, i }
        <div class="project-card {i < visibleCards ? '' : 'hidden'}">
            <ProjectCard {name} {description} {sourceCode} />
        </div>
    {/each}

    <div class="btn-container" class:centerButton={projects.length == 1}>
        {#if visibleCards >= 2}
            <button 
                on:click={scrollLeft}
                class="
                    border 
                    border-teal-500 
                    bg-teal-500 
                    text-white 
                    rounded-md px-4 py-2 m-2 
                    transition duration-500 ease 
                    select-none hover:bg-teal-600 
                    focus:outline-none 
                    focus:shadow-outline
                    btn-return"
            >
                Return
            </button>
        {/if} 
    
        {#if visibleCards < projects.length}
            <button 
                on:click={scrollRight}
                class="
                    border 
                    border-indigo-500 
                    bg-indigo-500 
                    text-white 
                    rounded-md px-4 py-2 m-2 
                    transition duration-500 ease 
                    select-none 
                    hover:bg-indigo-600 
                    focus:outline-none 
                    focus:shadow-outline 
                    btn-next
                "
            >
                Next
            </button>  
        {/if} 
    </div>
</div>

<style>
    .title {
        background: linear-gradient(90deg, rgba(49,183,231,1) 11%, rgba(0,119,192,1) 92%);
        color: white;
        font-size: revert-layer;
        text-align: center;
        font-family: initial;
    }

    .project-container {
        display: flex;
        flex-direction: column;
        overflow: hidden;
    }

    @keyframes slide-up {
        0% {
            opacity: 0;
            transform: translateY(100%);
        }
        100% {
            opacity: 1;
            transform: translateY(0);
        }
    }

    .project-card {
        min-width: 100%;
        margin-right: 20px;
        transition: transform 0.5s ease;
        animation: slide-up 0.5s ease-out;
    }

    .project-card.hidden {
        transform: translateX(-100%);
    }

    .project-card.shifted {
        transform: translateX(-200%);
    }

    .btn-container {
        text-align:center;
    }

    .centerButton {
        display:flex;
        justify-content:center;
    }

    .btn-return, .btn-next {
        width: 196px;
        margin-top: 22px;
    }

    .btn-next.hidden {
        display:none;
    }

    .btn-return.hidden {
        display:none;
    }
</style>
  