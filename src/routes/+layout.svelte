<script>
	import { onMount } from 'svelte';
	import '@fontsource/inter';
	import '@fontsource/jetbrains-mono';
	
	// Check for dark mode preference
	onMount(() => {
		const prefersDarkMode = window.matchMedia('(prefers-color-scheme: dark)').matches;
		document.body.classList.toggle('dark', prefersDarkMode);
	});
</script>

<div class="container">
	<slot />
</div>

<style>
	:global(:root) {
		--primary-color: #121212;
		--secondary-color: #f5f5f5;
		--accent-color: #666;
		--border-color: #ddd;
		--bg-color: #ffffff;
		--text-color: #121212;
	}

	:global(body.dark) {
		--primary-color: #f5f5f5;
		--secondary-color: #121212;
		--accent-color: #aaa;
		--border-color: #444;
		--bg-color: #121212;
		--text-color: #f5f5f5;
	}

	:global(body) {
		font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 
			'Open Sans', 'Helvetica Neue', sans-serif;
		margin: 0;
		padding: 0;
		background-color: var(--bg-color);
		color: var(--text-color);
		line-height: 1.6;
		font-size: 16px;
		transition: background-color 0.3s ease, color 0.3s ease;
	}

	:global(h1, h2, h3, h4, h5, h6) {
		font-family: 'Inter', sans-serif;
		font-weight: 700;
		margin-top: 1.5em;
		margin-bottom: 0.5em;
	}

	:global(h1) { font-size: 2.5rem; }
	:global(h2) { font-size: 2rem; }
	:global(h3) { font-size: 1.5rem; }
	:global(h4) { font-size: 1.25rem; }

	:global(a) {
		color: var(--primary-color);
		text-decoration: none;
		border-bottom: 1px solid var(--accent-color);
		transition: border-color 0.2s ease;
	}

	:global(a:hover) {
		border-color: var(--primary-color);
	}

	:global(section) {
		margin: 2rem 0;
		padding: 1rem 0;
		border-bottom: 1px solid var(--border-color);
	}

	:global(code) {
		font-family: 'JetBrains Mono', monospace;
		background-color: var(--secondary-color);
		color: var(--primary-color);
		padding: 0.2em 0.4em;
		border-radius: 3px;
	}

	.container {
		max-width: 1100px;
		margin: 0 auto;
		padding: 0 1.5rem;
	}

	@media (max-width: 768px) {
		.container {
			padding: 0 1rem;
		}
	}
</style>