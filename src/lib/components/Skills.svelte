<script>
    import { onMount } from 'svelte';
    import { fade } from 'svelte/transition';

    export let skillGroups = [
        {
            category: "LLM & AI Engineering",
            skills: [
                "Agentic AI Architecture Design using LangChain & LangGraph",
                "Agentic Flows & Advanced RAG",
                "LLM-reasoning Applications",
                "Textual Data Analytics using LLMs, BERT, Embedding models"
            ]
        },
        {
            category: "Programming Languages",
            skills: [
                "Python",
                "JavaScript",
                "Shell Scripting",
                "C/C++",
                "HTML",
                "CSS"
            ]
        },
        {
            category: "DevOps & Cloud",
            skills: [
                "Docker",
                "Kubernetes",
                "Azure",
                "OCP - Linux",
                "GitHub Actions (CI/CD workflow)",
                "Jenkins"
            ]
        },
        {
            category: "Data Science & ML",
            skills: [
                "Data Analysis",
                "Applied Machine Learning",
                "Pandas, Numpy, Matplotlib",
                "PyTorch, Keras"
            ]
        },
        {
            category: "Backend Development",
            skills: [
                "RESTful API Design",
                "Django REST",
                "Flask",
                "FastAPI"
            ]
        },
        {
            category: "Databases",
            skills: [
                "PostgreSQL", 
                "MongoDB", 
                "ElasticSearch", 
                "ChromaDB"
            ]
        },
        {
            category: "Soft Skills",
            skills: [
                "Technical Leadership",
                "Effective Communication",
                "Team Collaboration",
                "Result Oriented",
                "Problem Solving"
            ]
        }
    ];

    let visible = false;

    onMount(() => {
        visible = true;
    });
</script>

<section id="skills" class="skills">
    <h2>Skills</h2>

    <div class="skills-container">
        {#each skillGroups as group, i}
            {#if visible}
                <div class="skill-category" transition:fade={{ delay: i * 100, duration: 400 }}>
                    <h3>{group.category}</h3>
                    <ul class="skill-list">
                        {#each group.skills as skill}
                            <li class="skill-item">{skill}</li>
                        {/each}
                    </ul>
                </div>
            {/if}
        {/each}
    </div>
</section>

<style>
    .skills {
        margin: 3rem 0;
    }

    .skills-container {
        display: grid;
        grid-template-columns: 1fr 1fr;
        gap: 2rem;
    }

    h2, h3 {
        position: relative;
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
    
    h3::after {
        content: '';
        position: absolute;
        left: 0;
        bottom: -0.3rem;
        width: 2rem;
        height: 2px;
        background-color: var(--accent-color);
    }

    .skill-category {
        margin-bottom: 2rem;
    }

    .skill-list {
        list-style-type: disc;
        padding-left: 1.5rem;
        margin: 0.8rem 0 0 0;
    }

    .skill-item {
        padding: 0.3rem 0;
        font-size: 0.95rem;
    }

    @media (max-width: 768px) {
        .skills-container {
            grid-template-columns: 1fr;
        }
    }

    @media (min-width: 1200px) {
        .skills-container {
            grid-template-columns: repeat(3, 1fr);
        }
    }
</style>