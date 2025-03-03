<script>
    export let bio = `
        I am an AI Engineer with extensive experience in machine learning model development, 
        deployment, and optimization. Specializing in deep learning architectures and natural 
        language processing, I build scalable AI solutions that drive business value and 
        innovation. My expertise spans the entire ML lifecycle from data preprocessing to 
        production deployment and monitoring.
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