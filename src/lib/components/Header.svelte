<script>
    export let name = "John Doe";
    export let title = "AI Engineer";
    export let tagline = "Building intelligent systems that solve real-world problems";
</script>

<header class="header">
    <div class="header-content">
        <h1 class="name">{name}</h1>
        <h2 class="title">{title}</h2>
        <p class="tagline">{tagline}</p>
    </div>
</header>

<style>
    .header {
        padding: 4rem 0 3rem;
        text-align: center;
        border-bottom: 1px solid var(--border-color);
    }

    .header-content {
        max-width: 800px;
        margin: 0 auto;
    }

    .name {
        font-size: 3.5rem;
        margin: 0;
        letter-spacing: -0.02em;
        font-weight: 800;
    }

    .title {
        font-size: 1.8rem;
        font-weight: 500;
        color: var(--accent-color);
        margin: 0.5rem 0;
    }

    .tagline {
        font-size: 1.2rem;
        margin-top: 1rem;
        font-weight: 400;
    }

    @media (max-width: 768px) {
        .header {
            padding: 2rem 0;
        }

        .name {
            font-size: 2.5rem;
        }

        .title {
            font-size: 1.5rem;
        }
    }
</style>