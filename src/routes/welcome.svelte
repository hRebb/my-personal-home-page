<script>
    import { page } from '$app/stores'
</script>

<h1 class="title">
    Hi there, welcome to my Personal Profile
</h1>

<br />

<aside class="subtitle">
    <h2>
        Here you can find all sections in my Profile
    </h2>
    <li aria-current={$page.url.pathname === '/career' ? 'page' : undefined}>
        <a href="/career">Career Path</a>
    </li>
    <li aria-current={$page.url.pathname === '/projects' ? 'page' : undefined}>
        <a href="/projects">My Side Projects</a>
    </li>
    <li aria-current={$page.url.pathname === '/stack' ? 'page' : undefined}>
        <a href="/stack">My Technologies</a>
    </li>
    <li aria-current={$page.url.pathname === '/social' ? 'page' : undefined}>
        <a href="/social">Where to find me</a>
    </li>
</aside>

<style>
    .title {
        background: linear-gradient(90deg, rgba(49,183,231,1) 11%, rgba(0,119,192,1) 92%);
        color: white;
        font-size: revert-layer;
        text-align: center;
        font-family: initial;
    }

    .subtitle {
        background: linear-gradient(90deg, rgba(49,183,231,1) 11%, rgba(0,119,192,1) 92%);
        color: white;
        text-align: center;
    }
</style>