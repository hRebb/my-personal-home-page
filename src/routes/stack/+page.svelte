<script>
    import Front from "./front/front.svelte";
    import Back from "./back/back.svelte";
    import Devops from "./devops/devops.svelte";
    import Productivity from "./productivity/productivity.svelte";
</script>

<h1 class="title">
    My Stack
  </h1>

<div class="container frontend">
    <Front/>
</div>
<br>

<div class="container backend">
    <Back />
</div>
<br>

<div class="container devops">
    <Devops />
</div>
<br>

<div class="container productivity">
    <Productivity />
</div>