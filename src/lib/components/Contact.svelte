<script>
    import { fade } from 'svelte/transition';

    export let email = "ai.engineer@example.com";
    export let linkedin = "https://linkedin.com/in/ai-engineer";
    export let github = "https://github.com/ai-engineer";
    export let portfolio = "https://portfolio.ai-engineer.com";

    let name = '';
    let contactEmail = '';
    let message = '';
    let submitted = false;

    function handleSubmit() {
        // In a real implementation, you would send this data to a server
        console.log({ name, contactEmail, message });
        submitted = true;
        name = '';
        contactEmail = '';
        message = '';

        // Reset the submitted status after 5 seconds
        setTimeout(() => {
            submitted = false;
        }, 5000);
    }
</script>

<section id="contact" class="contact">
    <h2>Get In Touch</h2>
    
    <div class="contact-container">
        <div class="contact-info">
            <h3>Contact Information</h3>
            <p>Feel free to reach out through any of these channels or use the form to send me a direct message.</p>
            
            <div class="contact-links">
                <a href="mailto:{email}" class="contact-link">
                    <span class="icon">✉️</span>
                    <span class="text">{email}</span>
                </a>
                <a href={linkedin} target="_blank" rel="noopener noreferrer" class="contact-link">
                    <span class="icon">👔</span>
                    <span class="text">LinkedIn</span>
                </a>
                <a href={github} target="_blank" rel="noopener noreferrer" class="contact-link">
                    <span class="icon">💻</span>
                    <span class="text">GitHub</span>
                </a>
                <a href={portfolio} target="_blank" rel="noopener noreferrer" class="contact-link">
                    <span class="icon">🌐</span>
                    <span class="text">Portfolio</span>
                </a>
            </div>
        </div>
        
        <div class="contact-form">
            <h3>Send a Message</h3>
            
            {#if submitted}
                <div class="success-message" in:fade>
                    <p>Thank you for your message! I'll get back to you soon.</p>
                </div>
            {:else}
                <form on:submit|preventDefault={handleSubmit}>
                    <div class="form-group">
                        <label for="name">Name</label>
                        <input type="text" id="name" bind:value={name} required>
                    </div>
                    
                    <div class="form-group">
                        <label for="email">Email</label>
                        <input type="email" id="email" bind:value={contactEmail} required>
                    </div>
                    
                    <div class="form-group">
                        <label for="message">Message</label>
                        <textarea id="message" bind:value={message} rows="5" required></textarea>
                    </div>
                    
                    <button type="submit" class="submit-btn">Send Message</button>
                </form>
            {/if}
        </div>
    </div>
</section>

<style>
    .contact {
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
    
    .contact-container {
        display: grid;
        grid-template-columns: 1fr 1fr;
        gap: 3rem;
    }
    
    h3 {
        margin: 0 0 1rem;
    }
    
    .contact-info p {
        margin-bottom: 1.5rem;
        line-height: 1.6;
    }
    
    .contact-links {
        display: flex;
        flex-direction: column;
        gap: 1rem;
    }
    
    .contact-link {
        display: flex;
        align-items: center;
        padding: 0.8rem;
        border: 1px solid var(--border-color);
        border-radius: 8px;
        transition: background-color 0.3s ease, transform 0.3s ease;
    }
    
    .contact-link:hover {
        background-color: var(--secondary-color);
        transform: translateX(5px);
    }
    
    .icon {
        margin-right: 1rem;
        font-size: 1.2rem;
    }
    
    .form-group {
        margin-bottom: 1.5rem;
    }
    
    label {
        display: block;
        margin-bottom: 0.5rem;
        font-weight: 500;
    }
    
    input, textarea {
        width: 100%;
        padding: 0.8rem;
        border: 1px solid var(--border-color);
        border-radius: 4px;
        background-color: var(--bg-color);
        color: var(--text-color);
        font-family: 'Inter', sans-serif;
        font-size: 1rem;
    }
    
    input:focus, textarea:focus {
        outline: none;
        border-color: var(--primary-color);
    }
    
    .submit-btn {
        padding: 0.8rem 1.5rem;
        background-color: var(--primary-color);
        color: var(--secondary-color);
        border: none;
        border-radius: 4px;
        font-size: 1rem;
        font-weight: 500;
        cursor: pointer;
        transition: background-color 0.3s ease;
    }
    
    .submit-btn:hover {
        background-color: var(--accent-color);
    }
    
    .success-message {
        padding: 2rem;
        background-color: var(--secondary-color);
        color: var(--primary-color);
        border-radius: 8px;
        text-align: center;
    }
    
    @media (max-width: 768px) {
        .contact-container {
            grid-template-columns: 1fr;
        }
    }
</style>