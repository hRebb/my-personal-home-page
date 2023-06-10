<script>
    import Front from "./front/front.svelte";
    import Back from "./back/back.svelte";
    import Devops from "./devops/devops.svelte";
    import Productivity from "./productivity/productivity.svelte";
</script>

<h1 class="title">
    My Stack
</h1>

<div class="stack-tab frontend">
    <Front/>
</div>
<br>

<div class="stack-tab backend">
    <Back />
</div>
<br>

<div class="stack-tab devops">
    <Devops />
</div>
<br>

<div class="stack-tab productivity">
    <Productivity />
</div>

<style>
    @import "./stack.css";
</style>