<script lang="ts">
    import { onMount } from "svelte";
    import type { FetchResponse } from"node-fetch";

    let stackTechnique: string[] = [];

    onMount(async() => {
        try{
            const response: FetchResponse = await fetch('src/routes/stack/back/back.json');
            const data: {stackTechnique: string[]} = await response.json();
            stackTechnique = data.stackTechnique;
        } catch (error) {
            console.error('Erreur lors de la récupération des données JSON:', error);
        }
    })
</script>

<table>
    <thead>
        <th>
            Back-End
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
                    {#if item === 'PHP'}
                        <img src="https://img.shields.io/badge/php-%23777BB4.svg?style=for-the-badge&logo=php&logoColor=white" alt="PHP">
                    {:else if item === 'NodeJS'}
                        <img src="https://img.shields.io/badge/node.js-6DA55F?style=for-the-badge&logo=node.js&logoColor=white" alt="NodeJS">
                    {:else if item === 'Python'}
                        <img src="https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54" alt="Python">
                    {:else if item === 'Django'}
                        <img src="https://img.shields.io/badge/django-%23092E20.svg?style=for-the-badge&logo=django&logoColor=white" alt="Django">
                    {:else if item === 'MySQL'}
                        <img src="https://img.shields.io/badge/mysql-%2300f.svg?style=for-the-badge&logo=mysql&logoColor=white" alt="MySQL">
                    {:else if item === 'SQLite'}
                        <img src="https://img.shields.io/badge/SQLite-07405E?style=for-the-badge&logo=sqlite&logoColor=white" alt="SQLite">
                    {:else if item === 'MongoDB'}
                        <img src="https://img.shields.io/badge/MongoDB-%234ea94b.svg?style=for-the-badge&logo=mongodb&logoColor=white" alt="MongoDB">
                    {/if}
                </td>
            </tr>
        {/each}
    </tbody>
</table>