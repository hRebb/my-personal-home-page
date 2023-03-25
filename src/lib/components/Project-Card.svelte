<script>
    export let name = ""
    export let description = ""
    export let sourceCode = ""
</script>

<div class="max-w-sm rounded overflow-hidden shadow-lg bg-white tw-card">
    <div class="px-6 py-4 bg-gray-900 text-white">
      <h2 class="font-bold text-xl mb-2">{name}</h2>
    </div>
    <div class="px-6 py-4">
      <p class="text-gray-700 text-base">{description.slice(0, 80)}...</p>
      <p class="text-gray-700 text-base">
        <a href={sourceCode} class="underline">{sourceCode}</a>
      </p>
    </div>
</div>
    
<style>
    .tw-card { text-align: center; display: contents;}
</style>
