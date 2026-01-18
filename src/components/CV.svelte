<script>
	import { onMount, onDestroy } from 'svelte';
	import About from './sections/About.svelte';
	import Experience from './sections/Experience.svelte';
	import Skills from './sections/Skills.svelte';
	import Education from './sections/Education.svelte';
	import Contact from './sections/Contact.svelte';

	const tabs = [
		{ id: 'about', label: 'Обо мне', icon: '👤' },
		{ id: 'experience', label: 'Опыт', icon: '💼' },
		{ id: 'skills', label: 'Навыки', icon: '⚡' },
		{ id: 'education', label: 'Образование', icon: '🎓' },
		{ id: 'contact', label: 'Контакты', icon: '📧' }
	];	
	let activeTab = tabs[0].id;
	let isScrolled = false;

	function handleScroll() {
		isScrolled = window.scrollY > 60;
	}

	onMount(() => {
		handleScroll();
	 	window.addEventListener('scroll', handleScroll, { passive: true });
	});

	onDestroy(() => {
	 	window.removeEventListener('scroll', handleScroll);
	});
</script>

<div class="cv-container">
	<header class:scrolled={isScrolled}>
		<div class="header-content">
			<h1 class="title">Аркадий Чахалян</h1>
			<p class="subtitle">Frontеnd разработчик</p>
		</div>
	</header>

	<nav class="tabs-nav">
		{#each tabs as tab (tab.id)}
			<button
				class="tab-button"
				class:active={activeTab === tab.id}
				on:click={() => (activeTab = tab.id)}
			>
				<span class="icon">{tab.icon}</span>
				<span class="label">{tab.label}</span>
			</button>
		{/each}
	</nav>

	<main class="content-wrapper">
		{#if activeTab === 'about'}
			<About />
		{:else if activeTab === 'experience'}
			<Experience />
		{:else if activeTab === 'skills'}
			<Skills />
		{:else if activeTab === 'education'}
			<Education />
		{:else if activeTab === 'contact'}
			<Contact />
		{/if}
	</main>
</div>

<style>
	:global(:root) {
		--primary: #6366f1;
		--secondary: #8b5cf6;
		--accent: #ec4899;
		--bg-dark: #0f172a;
		--bg-light: #1e293b;
		--glass-bg: rgba(30, 41, 59, 0.8);
		--text-primary: #f1f5f9;
		--text-secondary: #cbd5e1;
		--border-color: rgba(148, 163, 184, 0.2);
	}

	:global(body) {
		background: linear-gradient(135deg, var(--bg-dark) 0%, #1a0f2e 100%);
		color: var(--text-primary);
		font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
		margin: 0;
		padding: 0;
	}

	.cv-container {
		min-height: 100vh;
		background: linear-gradient(135deg, var(--bg-dark) 0%, #1a0f2e 100%);
	}

	header {
		padding: 4rem 2rem;
		text-align: center;
		background: linear-gradient(135deg, rgba(99, 102, 241, 0.1) 0%, rgba(139, 92, 246, 0.1) 100%);
		border-bottom: 1px solid var(--border-color);
		position: sticky;
		top: 0;
		z-index: 90;
		transition: all 0.3s ease;
		backdrop-filter: blur(10px);
	}

	header.scrolled {
		transform: translateY(-35%);
		box-shadow: 0 10px 40px rgba(0, 0, 0, 0.3);
	}

	.header-content {
		max-width: 1000px;
		margin: 0 auto;
		animation: slideDown 0.6s ease-out;
		transition: transform 0.3s ease;
	}

	header.scrolled .header-content {
		transform: translateY(35%) scale(0.975);
	}

	.title {
		font-size: 3rem;
		font-weight: 800;
		margin: 0;
		background: linear-gradient(135deg, var(--primary) 0%, var(--accent) 100%);
		-webkit-background-clip: text;
		-webkit-text-fill-color: transparent;
		background-clip: text;
	}

	.subtitle {
		font-size: 1.25rem;
		color: var(--text-secondary);
		margin: 0.5rem 0 0 0;
		animation: fadeIn 0.8s ease-out 0.2s backwards;
	}

	.tabs-nav {
		display: flex;
		justify-content: center;
		gap: 1rem;
		padding: 2rem;
		flex-wrap: wrap;
		max-width: 1000px;
		margin: 0 auto;
		backdrop-filter: blur(10px);
	}

	.tab-button {
		display: flex;
		align-items: center;
		gap: 0.5rem;
		padding: 0.75rem 1.5rem;
		border: 2px solid var(--border-color);
		background: var(--glass-bg);
		color: var(--text-primary);
		border-radius: 50px;
		cursor: pointer;
		font-size: 1rem;
		font-weight: 600;
		transition: all 0.3s ease;
		backdrop-filter: blur(10px);
	}

	.tab-button:hover {
		border-color: var(--primary);
		background: rgba(99, 102, 241, 0.1);
		transform: translateY(-2px);
		box-shadow: 0 10px 30px rgba(99, 102, 241, 0.2);
	}

	.tab-button.active {
		border-color: var(--primary);
		background: linear-gradient(135deg, rgba(99, 102, 241, 0.2) 0%, rgba(139, 92, 246, 0.2) 100%);
		box-shadow: 0 10px 30px rgba(99, 102, 241, 0.3);
	}

	.icon {
		font-size: 1.25rem;
	}

	.label {
		display: none;
	}

	@media (min-width: 768px) {
		.label {
			display: inline;
		}
	}

	.content-wrapper {
		max-width: 1000px;
		margin: 0 auto;
		padding: 2rem;
		padding-top: 0;
		animation: fadeIn 0.5s ease-out;
	}

	@keyframes slideDown {
		from {
			opacity: 0;
			transform: translateY(-20px);
		}
		to {
			opacity: 1;
			transform: translateY(0);
		}
	}

	@keyframes fadeIn {
		from {
			opacity: 0;
		}
		to {
			opacity: 1;
		}
	}

	@media (max-width: 1024px) {
		.title {
			font-size: 2.5rem;
		}

		.subtitle {
			font-size: 1rem;
		}

		.tabs-nav {
			padding: 1.5rem 1rem;
			gap: 0.5rem;
		}

		.tab-button {
			padding: 0.65rem 1rem;
			font-size: 0.9rem;
		}
	}
</style>
