<script>
    import Header from '$lib/components/Header.svelte';
    import About from '$lib/components/About.svelte';
    import Skills from '$lib/components/Skills.svelte';
    import Education from '$lib/components/Education.svelte';
    import Experience from '$lib/components/Experience.svelte';
    import Contact from '$lib/components/Contact.svelte';
    import { onMount } from 'svelte';

    // Add smooth scrolling
    onMount(() => {
        const handleAnchorClick = (e) => {
            const href = e.target.getAttribute('href');
            if (href && href.startsWith('#')) {
                e.preventDefault();
                const targetId = href.substring(1);
                const targetElement = document.getElementById(targetId);
                if (targetElement) {
                    window.scrollTo({
                        top: targetElement.offsetTop - 20,
                        behavior: 'smooth'
                    });
                }
            }
        };

        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', handleAnchorClick);
        });

        return () => {
            document.querySelectorAll('a[href^="#"]').forEach(anchor => {
                anchor.removeEventListener('click', handleAnchorClick);
            });
        };
    });
</script>

<svelte:head>
    <title>AI Engineer | Resume & Portfolio</title>
    <meta name="description" content="Professional portfolio and resume of an AI Engineer specializing in machine learning, deep learning, and software development" />
</svelte:head>

<main>
    <Header 
        name="John Smith" 
        title="AI Engineer" 
        tagline="Building intelligent systems that solve real-world problems" 
    />

    <nav class="nav-bar">
        <ul>
            <li><a href="#about">About</a></li>
            <li><a href="#skills">Skills</a></li>
            <li><a href="#education">Education</a></li>
            <li><a href="#experience">Experience</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
    </nav>
    
    <About />
    <Skills />
    <Education />
    <Experience />
    <Contact />
    
    <footer>
        <p>&copy; {new Date().getFullYear()} John Smith. All rights reserved.</p>
    </footer>
</main>

<style>
    main {
        min-height: 100vh;
    }

    .nav-bar {
        position: sticky;
        top: 0;
        z-index: 100;
        background-color: var(--bg-color);
        border-bottom: 1px solid var(--border-color);
        padding: 1rem 0;
        margin-bottom: 2rem;
    }

    .nav-bar ul {
        display: flex;
        justify-content: center;
        padding: 0;
        margin: 0;
        list-style: none;
    }

    .nav-bar li {
        margin: 0 1rem;
    }

    .nav-bar a {
        text-decoration: none;
        font-weight: 500;
        padding: 0.5rem;
        border-bottom: 2px solid transparent;
        transition: border-color 0.2s ease;
    }

    .nav-bar a:hover {
        border-color: var(--primary-color);
    }

    footer {
        text-align: center;
        padding: 2rem 0;
        margin-top: 3rem;
        border-top: 1px solid var(--border-color);
        color: var(--accent-color);
    }

    @media (max-width: 768px) {
        .nav-bar {
            overflow-x: auto;
        }

        .nav-bar ul {
            width: max-content;
        }
    }
</style>
