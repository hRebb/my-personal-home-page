<script lang="ts">
    import Front from "./front/front.svelte";
    import Back from "./back/back.svelte";
    import Devops from "./devops/devops.svelte";
    import Productivity from "./productivity/productivity.svelte";

    import {onMount} from 'svelte';

    let activeTab: string = '';

    function showTab(tabName: string) {
        activeTab = tabName;
    }

    onMount(() => {
        const divs: NodeListOf<HTMLDivElement> = document.querySelectorAll('.stack-tab');
        divs.forEach((div: HTMLDivElement) => {
            div.style.display = 'none';
        });
    });
</script>

<h1 class="title">
    My Stack
</h1>

<div class="stack-tab frontend" style="{activeTab === 'frontend' ? 'display: block;' : 'display: none;'}">
    <Front/>
</div>
<br>

<div class="stack-tab backend" style="{activeTab === 'backend' ? 'display: block;' : 'display: none;'}">
    <Back />
</div>
<br>

<div class="stack-tab devops" style="{activeTab === 'devops' ? 'display: block;' : 'display: none;'}">
    <Devops />
</div>
<br>

<div class="stack-tab productivity" style="{activeTab === 'productivity' ? 'display: block;' : 'display: none;'}">
    <Productivity />
</div>
<br>

<div class="section-btn flex justify-center">
    <button class="btn-front" on:click={() => showTab('frontend')}>
        FrontEnd
    </button>
    <button class="btn-back" on:click={() => showTab('backend')}>
        BackEnd
    </button>
    <button class="btn-devops" on:click={() => showTab('devops')}>
        DevOps
    </button>
    <button class="btn-prod" on:click={() => showTab('productivity')}>
        Productivity
    </button>
    
</div>

<style>
    @import "./stack.css";
</style>