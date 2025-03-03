<script>
    import { slide } from 'svelte/transition';

    export let education = [
        {
            degree: 'MSc. in Computer Science',
            focus: 'Specialized in Software Engineering – GPA: 4.0',
            institution: 'University of Calgary',
            year: '2020 – 2022',
            achievements: [
                'One of two students to be awarded Departmental Research Scholarship for $11k',
                'Fall-Winter 2022'
            ]
        },
        {
            degree: 'BSc. in Computer Science',
            focus: 'Graduated top 5% ranking student – GPA: 3.85',
            institution: 'Iran University of Science and Technology',
            year: '2015 – 2019',
            achievements: [
                'Awarded Scholarship for Best Student of the year',
                '2016'
            ]
        }
    ];

    export let certifications = [
        {
            name: 'TensorFlow Developer Certificate',
            issuer: 'Google',
            year: '2023'
        },
        {
            name: 'AWS Certified Machine Learning - Specialty',
            issuer: 'Amazon Web Services',
            year: '2022'
        },
        {
            name: 'Deep Learning Specialization',
            issuer: 'DeepLearning.AI',
            year: '2021'
        }
    ];
</script>

<section id="education" class="education">
    <h2>Education</h2>
    
    <div class="education-container">
        <div class="degrees">
            <h3>Academic Degrees</h3>
            <div class="timeline">
                {#each education as edu, i}
                    <div class="timeline-item" in:slide={{ delay: i * 150, duration: 400 }}>
                        <div class="timeline-dot"></div>
                        <div class="timeline-content">
                            <div class="time-period">{edu.year}</div>
                            <h4>{edu.degree}</h4>
                            <p class="institution">{edu.institution}</p>
                            <p class="focus">{edu.focus}</p>
                            {#if edu.achievements && edu.achievements.length > 0}
                                <ul class="achievements">
                                    {#each edu.achievements as achievement}
                                        <li>{achievement}</li>
                                    {/each}
                                </ul>
                            {/if}
                        </div>
                    </div>
                {/each}
            </div>
        </div>
        
        <div class="certifications">
            <h3>Certifications</h3>
            <div class="cert-list">
                {#each certifications as cert, i}
                    <div class="cert-item" in:slide={{ delay: i * 150, duration: 400 }}>
                        <div class="cert-year">{cert.year}</div>
                        <div class="cert-details">
                            <h4>{cert.name}</h4>
                            <p>Issued by {cert.issuer}</p>
                        </div>
                    </div>
                {/each}
            </div>
        </div>
    </div>
</section>

<style>
    .education {
        margin: 3rem 0;
    }
    
    .education-container {
        display: grid;
        grid-template-columns: 1fr 1fr;
        gap: 3rem;
    }
    
    h2, h3 {
        position: relative;
    }
    
    h2::after, h3::after {
        content: '';
        position: absolute;
        left: 0;
        bottom: -0.5rem;
        width: 3rem;
        height: 3px;
        background-color: var(--accent-color);
    }
    
    .timeline {
        position: relative;
        margin-top: 2rem;
        padding-left: 2rem;
    }
    
    .timeline::before {
        content: '';
        position: absolute;
        left: 0;
        top: 0;
        height: 100%;
        width: 1px;
        background-color: var(--accent-color);
    }
    
    .timeline-item {
        position: relative;
        margin-bottom: 2rem;
    }
    
    .timeline-dot {
        position: absolute;
        left: -2rem;
        top: 0.5rem;
        width: 1rem;
        height: 1rem;
        border-radius: 50%;
        background-color: var(--primary-color);
        border: 2px solid var(--bg-color);
    }
    
    .time-period {
        display: inline-block;
        padding: 0.3rem 0.8rem;
        background-color: var(--secondary-color);
        color: var(--primary-color);
        border-radius: 4px;
        font-size: 0.9rem;
        font-weight: 500;
        margin-bottom: 0.5rem;
    }
    
    .timeline-content h4 {
        margin: 0.5rem 0;
        font-size: 1.1rem;
    }
    
    .institution {
        font-weight: 500;
        margin: 0;
    }
    
    .focus {
        color: var(--accent-color);
        font-size: 0.95rem;
        margin: 0.3rem 0 0;
    }
    
    .cert-list {
        margin-top: 2rem;
    }
    
    .cert-item {
        display: flex;
        margin-bottom: 1.5rem;
        padding-bottom: 1rem;
        border-bottom: 1px solid var(--border-color);
    }
    
    .cert-item:last-child {
        border-bottom: none;
    }
    
    .cert-year {
        flex: 0 0 4rem;
        font-weight: 600;
    }
    
    .cert-details h4 {
        margin: 0 0 0.3rem;
        font-size: 1.1rem;
    }
    
    .cert-details p {
        margin: 0;
        font-size: 0.95rem;
        color: var(--accent-color);
    }
    
    @media (max-width: 768px) {
        .education-container {
            grid-template-columns: 1fr;
            gap: 2rem;
        }
    }

    .achievements {
        margin: 0.5rem 0 0;
        padding-left: 1.2rem;
        list-style-type: disc;
    }
    
    .achievements li {
        margin-bottom: 0.3rem;
        font-size: 0.9rem;
        color: var(--accent-color);
    }
</style>