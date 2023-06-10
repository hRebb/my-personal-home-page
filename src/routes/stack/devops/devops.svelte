<script lang="ts">
    import { onMount } from "svelte";
    import type { FetchResponse } from"node-fetch";

    let stackTechnique: string[] = [];

    onMount(async() => {
        try{
            const response: FetchResponse = await fetch('src/routes/stack/devops/devops.json');
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
            DevOps Tools
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
                    {#if item === 'Docker'}
                        <img src="https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white" alt="Docker">
                    {:else if item === 'Vagrant'}
                        <img src="https://img.shields.io/badge/vagrant-%231563FF.svg?style=for-the-badge&logo=vagrant&logoColor=white" alt="Vagrant">
                    {:else if item === 'GitHub Actions'}
                        <img src="https://img.shields.io/badge/github%20actions-%232671E5.svg?style=for-the-badge&logo=githubactions&logoColor=white" alt="GitHub Actions">
                    {:else if item === 'Virtualbox'}
                        <img src="https://img.shields.io/badge/VirtualBox-183A61.svg?style=for-the-badge&logo=VirtualBox&logoColor=white" alt="Virtualbox">
                    {:else if item === 'SonarQube'}
                        <img src="https://img.shields.io/badge/SonarQube-4E9BCD.svg?style=for-the-badge&logo=SonarQube&logoColor=white" alt="SonarQube">
                    {:else if item === 'SonarCloud'}
                        <img src="https://img.shields.io/badge/SonarCloud-F3702A.svg?style=for-the-badge&logo=SonarCloud&logoColor=white" alt="SonarCloud">
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