<script lang="ts">
    import { onMount } from "svelte";
    let stackTechnique = [];

    onMount(async() => {
        try{
            const response = await fetch('src/routes/stack/front/front.json');
            const data = await response.json();
            stackTechnique = data.stackTechnique;
        } catch(error) {
            console.error('Erreur lors de la récupération des données JSON:', error);
        }
    })

    
</script>

<table>
    <thead>
        <tr>
            <th>Title</th>
            <th>Badge</th>
        </tr>
    </thead>
    <tbody>
        {#each stackTechnique as item }
            <tr>
                <td>
                    {item}
                </td>
                <td>
                    {#if item === 'HTML'}
                        <img src="https://img.shields.io/badge/-HTML5-E44D26?style=for-the-badge&logo=html5&logoColor=white" alt="HTML5">
                    {:else if item === 'CSS'}
                        <img src="https://img.shields.io/badge/-CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white" alt="CSS3">
                    {:else if item === 'SCSS'}
                        <img src="https://img.shields.io/badge/-SCSS-CB6699?style=for-the-badge&logo=sass&logoColor=white" alt="SCSS">
                    {:else if item === 'JS'}
                        <img src="https://img.shields.io/badge/-Javascript-F0DB4F?style=for-the-badge&logo=javascript&logoColor=323330" alt="Javascript">
                    {:else if item === 'TS'}
                        <img src="https://img.shields.io/badge/-Typescript-3178C6?style=for-the-badge&logo=typescript&logoColor=white" alt="Typescript">
                    {:else if item === 'REACT'}
                        <img src="https://img.shields.io/badge/-ReactJs-61DAFB?style=for-the-badge&logo=react&logoColor=white" alt="ReactJS">
                    {:else if item === 'BOOTSTRAP'}
                        <img src="https://img.shields.io/badge/bootstrap-%23563D7C.svg?style=for-the-badge&logo=bootstrap&logoColor=white" alt="Bootstrap">
                    {:else if item === 'SVELTE'}
                        <img src="https://img.shields.io/badge/svelte-%23f1413d.svg?style=for-the-badge&logo=svelte&logoColor=white" alt="Svelte">
                    {/if}
                </td>
            </tr>
        {/each}
    </tbody>
</table>