<script lang="ts">
    import { onMount } from "svelte";
    import type { FetchResponse } from"node-fetch";

    let stackTechnique: string[] = [];

    onMount(async() => {
        try{
            const response: FetchResponse = await fetch('src/routes/stack/productivity/productivity.json');
            const data: {stackTechnique: string[]} = await response.json();
            stackTechnique = data.stackTechnique;
        } catch (error) {
            console.error('Erreur lors de la récupération des données JSON:', error);
        }
    })
</script>

<table>
    <thead>
        <th class="sub">
            Productivity Tools
        </th>
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
                    {#if item === 'Git'}
                        <img src="https://img.shields.io/badge/git-%23F05033.svg?style=for-the-badge&logo=git&logoColor=white" alt="Git">
                    {:else if item === 'GitHub'}
                        <img src="https://img.shields.io/badge/github-%23121011.svg?style=for-the-badge&logo=github&logoColor=white" alt="GitHub">
                    {:else if item === 'GitLab'}
                        <img src="https://img.shields.io/badge/gitlab-%23181717.svg?style=for-the-badge&logo=gitlab&logoColor=white" alt="GitLab">
                    {:else if item === 'Firefox'}
                        <img src="https://img.shields.io/badge/Firefox-FF7139?style=for-the-badge&logo=Firefox-Browser&logoColor=white" alt="Firefox">
                    {:else if item === 'Canva'}
                        <img src="https://img.shields.io/badge/Canva-%2300C4CC.svg?&style=for-the-badge&logo=Canva&logoColor=white" alt="Canva">
                    {:else if item === 'Figma'}
                        <img src="https://img.shields.io/badge/Figma-F24E1E?style=for-the-badge&logo=figma&logoColor=white" alt="Figma">
                    {:else if item === 'Trello'}
                        <img src="https://img.shields.io/badge/Trello-0052CC?style=for-the-badge&logo=trello&logoColor=white" alt="Trello">
                    {:else if item === 'Vite'}
                        <img src="https://img.shields.io/badge/vite-%23646CFF.svg?style=for-the-badge&logo=vite&logoColor=white" alt="Vite">
                    {:else if item === 'Vercel'}
                        <img src="https://img.shields.io/badge/vercel-%23000000.svg?style=for-the-badge&logo=vercel&logoColor=white" alt="Vercel">
                    {/if}
                </td>
            </tr>
        {/each}
    </tbody>
</table>

<style>
    .sub {
        padding-left: 180px;
    }
</style>