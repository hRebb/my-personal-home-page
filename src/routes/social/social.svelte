<script lang="ts">
    let showModalLinkedin: boolean = false;
    let showModalGitHub: boolean = false;

    function openLinkedin(): boolean {
        showModalLinkedin = true;
        return showModalLinkedin;
    }

    function openGithub(): boolean {
        showModalGitHub = true;
        return showModalGitHub;
    }

    function closeModal(): boolean {
        showModalLinkedin = false;
        showModalGitHub = false;
        return showModalLinkedin && showModalGitHub;
    }
</script>

<h1 class="title">
    Where to find me in social network
</h1>

<div class="modals-btns">
    <button class="border border-indigo-500 bg-indigo-500 text-white rounded-md px-4 py-2 m-2 transition duration-500 ease select-none hover:bg-indigo-600 focus:outline-none focus:shadow-outline btn-next  s-7H1i5azzBsTx" on:click={openLinkedin}>
        LinkedIn
    </button>
    <button class="border border-gray-700 bg-gray-700 text-white rounded-md px-4 py-2 m-2 transition duration-500 ease select-none hover:bg-gray-800 focus:outline-none focus:shadow-outline" on:click={openGithub}>
        GitHub
    </button>
</div>

{#if showModalLinkedin || showModalGitHub}
    <!-- svelte-ignore a11y-click-events-have-key-events -->
    <div class='overlay' on:click={closeModal}></div>
    <div class="modal">
        {#if showModalLinkedin}
           <a href="https://www.linkedin.com/in/hamza-rebbani-b1680725a/" target="_blank">
                My Linkedin Profile
            </a>
        {:else}
            <a href="https://github.com/hRebb" target="_blank">
                My GitHub Profile
            </a>
        {/if}
    </div>
{/if}

<style>
    @import '../main.css';
    @import './social.css';
</style>

