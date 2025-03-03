<script>
    import { onMount } from 'svelte';
    import { fade } from 'svelte/transition';

    export let projects = [
        {
            title: 'Neural Document Parser',
            description: 'A deep learning system that extracts structured information from scanned documents with 95% accuracy.',
            technologies: ['PyTorch', 'Computer Vision', 'OCR', 'Transformers'],
            link: 'https://github.com/username/neural-document-parser'
        },
        {
            title: 'Autonomous Decision Framework',
            description: 'A reinforcement learning framework for optimizing complex business decisions in uncertain environments.',
            technologies: ['TensorFlow', 'Reinforcement Learning', 'Bayesian Methods'],
            link: 'https://github.com/username/autonomous-decision-framework'
        },
        {
            title: 'NLP Customer Support Bot',
            description: 'A production-ready conversational AI system that handles customer inquiries with human-like response quality.',
            technologies: ['BERT', 'FastAPI', 'Docker', 'Kubernetes'],
            link: 'https://github.com/username/nlp-support-bot'
        },
        {
            title: 'Distributed ML Training Platform',
            description: 'An MLOps platform for distributed training across heterogeneous computing resources.',
            technologies: ['PyTorch', 'Ray', 'Kubernetes', 'AWS'],
            link: 'https://github.com/username/distributed-ml-platform'
        }
    ];

    let visible = false;

    onMount(() => {
        visible = true;
    });
</script>

<section id="projects" class="projects">
    <h2>Featured Projects</h2>
    
    <div class="projects-grid">
        {#each projects as project, i}
            {#if visible}
                <div class="project-card" in:fade={{ delay: i * 150, duration: 500 }}>
                    <h3>{project.title}</h3>
                    <p>{project.description}</p>
                    <div class="technologies">
                        {#each project.technologies as tech}
                            <span class="tech-tag">{tech}</span>
                        {/each}
                    </div>
                    <a href={project.link} target="_blank" rel="noopener noreferrer" class="project-link">
                        View Project <span class="arrow">→</span>
                    </a>
                </div>
            {/if}
        {/each}
    </div>
</section>

<style>
    .projects {
        margin: 3rem 0;
    }
    
    h2 {
        position: relative;
        margin-bottom: 2rem;
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
    
    .projects-grid {
        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
        gap: 2rem;
    }
    
    .project-card {
        padding: 1.5rem;
        border: 1px solid var(--border-color);
        border-radius: 8px;
        transition: transform 0.3s ease, box-shadow 0.3s ease;
        display: flex;
        flex-direction: column;
        height: 100%;
    }
    
    .project-card:hover {
        transform: translateY(-5px);
        box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
    }
    
    h3 {
        margin: 0 0 1rem;
        font-size: 1.3rem;
    }
    
    .project-card p {
        margin: 0 0 1.5rem;
        line-height: 1.5;
        flex-grow: 1;
    }
    
    .technologies {
        display: flex;
        flex-wrap: wrap;
        gap: 0.5rem;
        margin-bottom: 1.5rem;
    }
    
    .tech-tag {
        font-size: 0.8rem;
        padding: 0.2rem 0.5rem;
        background-color: var(--secondary-color);
        color: var(--primary-color);
        border-radius: 4px;
    }
    
    .project-link {
        display: inline-flex;
        align-items: center;
        font-weight: 600;
        margin-top: auto;
        padding-top: 1rem;
        border-bottom: 2px solid transparent;
        transition: border-color 0.2s ease;
    }
    
    .project-link:hover {
        border-color: var(--primary-color);
    }
    
    .arrow {
        margin-left: 0.5rem;
        transition: transform 0.2s ease;
    }
    
    .project-link:hover .arrow {
        transform: translateX(5px);
    }
    
    @media (max-width: 768px) {
        .projects-grid {
            grid-template-columns: 1fr;
        }
    }
</style>