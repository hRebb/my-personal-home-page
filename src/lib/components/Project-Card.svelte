<script>
    export let name = ""
    export let description = ""
    export let sourceCode = ""
</script>

<div>
    <h2>
        {name}
    </h2>
    <p>
        {description.slice(0, 80)}...
    </p>
    <p>
        <a href={sourceCode}>
            {sourceCode}
        </a>
    </p>
</div>