<script>
    import { slide } from 'svelte/transition';

    export let experiences = [
        {
            title: 'Technical Lead – AI Engineering',
            company: 'ROYAL BANK OF CANADA (RBC)',
            period: 'Jan 2023 - Present',
            description: 'Two times award winning Tech-Lead guiding a team of seven engineers in multiple complex projects spearheading the proposal and designing new technologies at RBC.',
            achievements: [
                'Won the Leadership Model Award of 2023 in the RBC\'s Technology and Operations department.',
                'Spearheaded the adoption of Large Language Models (LLMs) into RBC\'s DevOps department, resulting in three key products:',
                '1. An LLM-powered ticket analysis and resolution system which resulted in reducing the average ticket closing time by 27%.',
                '2. A developer chatbot assistant integrated with multiple knowledge-bases using advanced RAG and LLM-agents to enhance development workflows and assist the developers in their CI/CD pipelines.',
                '3. An AI Slack Bot automatically resolving 22% of the issues using collaborating LLM-agents revolutionizing the app-support team.',
                'Played a key role in transitioning the RBC\'s main DevOps platform from a Jenkins-based system to GitHub Actions by establishing the underlying infrastructure for adopting GitHub Actions to facilitate the transition.',
                'Laid the foundation of GH Actions runners hosted in multiple internally managed platforms such as Azure and OCP4.',
                'Conducted extensive analysis of the company\'s DevOps usage data and reverse engineered the current RBC\'s main DevOps platform proving that moving towards GH Actions improves the average CI/CD pipeline execution time up to 3.5x.',
                'Introduced a new metric called "Consecutive Failure" changing the way RBC measures DevOps systems productivity which led to convincing the executives to approve the transition from Jenkins to GH Actions.',
                'Successfully mentored and guided three interns in multiple projects exceptionally improving their team working and coding skills.'
            ],
            tools: 'LangChain, LangGraph, Django, Docker, Azure, OCP4, Kubernetes, GitHub Actions, ChromaDB, ElasticSearch, PostgreSQL'
        },
        {
            title: 'Software Engineer & Technical Co-Founder',
            company: 'PORSLINE',
            period: 'Aug 2016 - Aug 2020',
            description: 'Porsline is the most successful online survey software company in the founding country, Turkey and the Middle East. The software is built for business developers and researchers to create smart questionnaires and analyze the results effectively.',
            achievements: [
                'Laid the foundation of the company\'s main software and helped recruit and develop the tech-team.',
                'Reengineered the underlying backend for the reporting subsystem, improving the backend reporting system performance by 15x.',
                'Implemented and designed the Front-End (AngularJS) and Back-End API (Django) for one of the key and most used features of the product – creating and editing surveys.',
                'Developed a scheduled-notifications system for survey responses as a microservice, posting now up to millions of notifications per day using Python Asyncio, crontab, and RabbitMQ.'
            ],
            tools: 'Python, Django, JS, PostgreSQL, Django REST, Docker, Git, Linux, Asyncio, RabbitMQ, Redis, AngularJS'
        }
    ];
</script>

<section id="experience" class="experience">
    <h2>Professional Experience</h2>
    
    <div class="experience-container">
        {#each experiences as exp, i}
            <div class="experience-item" in:slide={{ delay: i * 150, duration: 400 }}>
                <div class="experience-header">
                    <div class="title-company">
                        <h3>{exp.title}</h3>
                        <div class="company">{exp.company}</div>
                    </div>
                    <div class="period">{exp.period}</div>
                </div>
                
                <p class="description">{exp.description}</p>
                
                <div class="achievements">
                    <h4>Key Achievements:</h4>
                    <ul>
                        {#each exp.achievements as achievement}
                            <li>{achievement}</li>
                        {/each}
                    </ul>
                </div>
                
                {#if exp.tools}
                    <div class="tools">
                        <h4>Tools:</h4>
                        <p>{exp.tools}</p>
                    </div>
                {/if}
            </div>
        {/each}
    </div>
</section>

<style>
    .experience {
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
    
    .experience-item {
        padding: 1.5rem;
        margin-bottom: 1.5rem;
        border: 1px solid var(--border-color);
        border-radius: 8px;
        transition: transform 0.3s ease, box-shadow 0.3s ease;
    }
    
    .experience-item:hover {
        transform: translateY(-5px);
        box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
    }
    
    .experience-header {
        display: flex;
        justify-content: space-between;
        align-items: flex-start;
        margin-bottom: 1rem;
    }
    
    h3 {
        margin: 0 0 0.3rem;
        font-size: 1.3rem;
    }
    
    .company {
        font-size: 1rem;
        font-weight: 500;
    }
    
    .period {
        font-size: 0.9rem;
        background-color: var(--secondary-color);
        color: var(--primary-color);
        padding: 0.3rem 0.8rem;
        border-radius: 4px;
        font-weight: 500;
    }
    
    .description {
        margin: 0.8rem 0;
        line-height: 1.6;
    }
    
    .achievements h4, .tools h4 {
        font-size: 1rem;
        margin: 1rem 0 0.5rem;
    }
    
    .achievements ul {
        margin: 0.5rem 0 0;
        padding-left: 1.2rem;
    }
    
    .achievements li {
        margin-bottom: 0.5rem;
        line-height: 1.5;
    }
    
    .tools {
        margin-top: 1rem;
        padding-top: 0.8rem;
        border-top: 1px solid var(--border-color);
    }
    
    .tools p {
        margin: 0.3rem 0 0;
        font-family: 'JetBrains Mono', monospace;
        font-size: 0.9rem;
    }
    
    @media (max-width: 768px) {
        .experience-header {
            flex-direction: column;
        }
        
        .period {
            margin-top: 0.5rem;
        }
    }
</style>