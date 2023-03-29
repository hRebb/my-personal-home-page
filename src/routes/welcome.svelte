<script>
    import { page } from '$app/stores'
</script>

<body>
    <h1 class="title">
        Hi there, welcome to my Personal Profile
    </h1>
    <br />
    
    <aside class="bg-transparent border border-gray-300 rounded-lg p-6 w-full subtitle">
        <p>
            I'm Rebbani Hamza, a young web developer who will be working
            on few different side projects to improve my experience and skills.
        </p>
        <br>

        <h2 class="text-xl font-bold mb-4">Here are all the sections of my profile</h2>
        <br>

        <ul class="list-none">
          <li aria-current={$page.url.pathname === '/career' ? 'page' : undefined} class="my-4">
            <a href="/career" class="font-bold">Career Path</a>
          </li>
          <li aria-current={$page.url.pathname === '/projects' ? 'page' : undefined} class="my-4">
            <a href="/projects" class="font-bold">Side Projects</a>
          </li>
          <li aria-current={$page.url.pathname === '/stack' ? 'page' : undefined} class="my-4">
            <a href="/stack" class="font-bold">My Technical Stack</a>
          </li>
          <li aria-current={$page.url.pathname === '/social' ? 'page' : undefined} class="my-4">
            <a href="/social" class="font-bold">Where to find me</a>
          </li>
        </ul>
      </aside>
</body>
  
<style>
    @import 'main.css';

    .title {
        background: linear-gradient(90deg, rgba(49,183,231,1) 11%, rgba(0,119,192,1) 92%);
        font-size: revert-layer;
        text-align: center;
    }

    .subtitle {
        background: linear-gradient(90deg, rgba(49,183,231,1) 11%, rgba(0,119,192,1) 92%);
        text-align: center;
    }

    aside {
        height: 450px;
        font-size: large;
    }
</style>