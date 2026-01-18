<script>
	import AnimatedCard from '../AnimatedCard.svelte';

	const education = [
		{
			degree: 'Arctic Adventure Tourism',
			school: 'The Arctic University of Norway (UiT)',
			year: '2020',
			description: 'Бакалавриат на английском язык'
		},
		{
			degree: 'Финансовый менеджмент',
			school: 'Северный (Арктический) Федеральный Университет (САФУ)',
			year: '2013-2017',
			description: 'Бакалавриат'
		},
	];
</script>

<div class="education-section">
	<h2>Образование</h2>
	<div class="education-list">
		{#each education as edu, index (index)}
			<AnimatedCard delay={index * 0.1}>
				<div class="education-card">
					<div class="card-icon">🎓</div>
					<div class="card-content">
						<h3>{edu.degree}</h3>
						<p class="school">{edu.school}</p>
						<p class="year">{edu.year}</p>
						<p class="description">{edu.description}</p>
					</div>
				</div>
			</AnimatedCard>
		{/each}
	</div>
</div>

<style>
	.education-section {
		padding: 1rem 0;
	}

	h2 {
		font-size: 2rem;
		margin-bottom: 2rem;
		background: linear-gradient(135deg, var(--primary) 0%, var(--accent) 100%);
		-webkit-background-clip: text;
		-webkit-text-fill-color: transparent;
		background-clip: text;
	}

	.education-list {
		display: flex;
		flex-direction: column;
		gap: 1.5rem;
	}

	.education-card {
		display: flex;
		gap: 1.5rem;
		background: var(--glass-bg);
		border: 1px solid var(--border-color);
		border-radius: 12px;
		padding: 2rem;
		backdrop-filter: blur(10px);
		transition: all 0.3s ease;
	}

	.education-card:hover {
		border-color: var(--primary);
		box-shadow: 0 10px 30px rgba(99, 102, 241, 0.2);
		transform: translateX(8px);
	}

	.card-icon {
		font-size: 3rem;
		flex-shrink: 0;
	}

	.card-content {
		flex: 1;
	}

	h3 {
		margin: 0 0 0.5rem 0;
		font-size: 1.2rem;
		color: var(--text-primary);
	}

	.school {
		margin: 0.25rem 0;
		color: var(--accent);
		font-weight: 600;
	}

	.year {
		margin: 0.25rem 0 0.75rem 0;
		font-size: 0.9rem;
		color: var(--primary);
		font-weight: 600;
	}

	.description {
		margin: 0;
		color: var(--text-secondary);
		line-height: 1.6;
	}
</style>
