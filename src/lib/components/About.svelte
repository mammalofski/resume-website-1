<script>
    export let bio = `
        Award-winning AI Engineering Technical Lead with expertise in designing and implementing AI-powered 
        solutions for enterprise environments. Specializing in LLM-based applications, agentic AI architectures, 
        and advanced RAG systems. My work at RBC has demonstrated measurable productivity improvements 
        through AI adoption, with tangible results like reducing ticket closing time by 27% and automating 22% of 
        support issues through LLM-agent solutions. With a strong background in both software engineering and AI, 
        I bridge the gap between cutting-edge AI research and practical business applications to deliver 
        transformative technical solutions.
    `;
</script>

<section id="about" class="about">
    <h2>About Me</h2>
    <div class="bio">
        <p>{bio}</p>
    </div>
</section>

<style>
    .about {
        margin: 3rem 0;
    }

    .bio {
        font-size: 1.1rem;
        line-height: 1.6;
        max-width: 800px;
    }

    h2 {
        position: relative;
        display: inline-block;
        margin-bottom: 1.5rem;
    }

    h2::after {
        content: '';
        position: absolute;
        left: 0;
        bottom: -0.5rem;
        width: 3rem;
        height: 3px;
        background-color: var(--accent-color);
    }
</style>