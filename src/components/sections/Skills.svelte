<script>
	import AnimatedCard from '../AnimatedCard.svelte';
	import SkillBar from '../SkillBar.svelte';

	const skillCategories = [
		{
			category: 'Frontend',
			skills: [
				{ name: 'HTML5', level: 90 },
				{ name: 'CSS3 / SCSS / CSS in JS', level: 95 },
				{ name: 'JavaScript', level: 87 },
				{ name: 'TypeScript', level: 90 },
				{ name: 'React', level: 96 },
				{ name: 'Redux / RTK', level: 92 },
				{ name: 'Svelte', level: 55 },
				{ name: 'MaterialUI', level: 70 },
				{ name: 'Backbone.js', level: 65 },
				{ name: 'jQuery', level: 45 },
			]
		},
		{
			category: 'Backend',
			skills: [
				{ name: 'Node.js', level: 68 },
				{ name: 'Java', level: 35 },
				{ name: 'REST APIs', level: 85 },
				{ name: 'REST APIs', level: 74 },
				{ name: 'Express', level: 60 },
				{ name: 'NextJS', level: 62 },
				{ name: 'MongoDB / Mongoose', level: 55 },
				{ name: 'NoSQL', level: 50 },
				{ name: 'Firebase', level: 30 },
				{ name: 'Microservices', level: 40 },
			]
		},
		{
			category: 'Tools & DevOps',
			skills: [
				{ name: 'Git / GitHub', level: 75 },
				{ name: 'Docker', level: 56 },
				{ name: 'CI/CD', level: 50 },
				{ name: 'Webpack / Vite', level: 80 },
				{ name: 'ESLint / Prettier', level: 68 },
				{ name: 'Figma', level: 58 },
			]
		},
		{
			category: 'Языки',
			skills: [
				{ name: 'Русский', level: 100 },
				{ name: 'Английский', level: 75 },
				{ name: 'Армянский', level: 55 },
			]
		}
	];
</script>

<div class="skills-section">
	<h2>Навыки</h2>
	<div class="skills-grid">
		{#each skillCategories as category, catIndex (catIndex)}
			<AnimatedCard delay={catIndex * 0.1}>
				<div class="category-card">
					<h3>{category.category}</h3>
					<div class="skills-list">
						{#each category.skills as skill, skillIndex (skillIndex)}
							<div class="skill-item" style="--delay: {(catIndex * 5 + skillIndex) * 0.05}s">
								<div class="skill-header">
									<span class="skill-name">{skill.name}</span>
									<span class="skill-level">{skill.level}%</span>
								</div>
								<SkillBar level={skill.level} />
							</div>
						{/each}
					</div>
				</div>
			</AnimatedCard>
		{/each}
	</div>
</div>

<style>
	.skills-section {
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

	.skills-grid {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
		gap: 2rem;
	}

	.category-card {
		background: var(--glass-bg);
		border: 1px solid var(--border-color);
		border-radius: 12px;
		padding: 2rem;
		backdrop-filter: blur(10px);
		transition: all 0.3s ease;
	}

	.category-card:hover {
		border-color: var(--primary);
		box-shadow: 0 10px 30px rgba(99, 102, 241, 0.2);
		transform: translateY(-4px);
	}

	h3 {
		margin-top: 0;
		margin-bottom: 1.5rem;
		font-size: 1.3rem;
		color: var(--accent);
	}

	.skills-list {
		display: flex;
		flex-direction: column;
		gap: 1.2rem;
	}

	.skill-item {
		animation: slideInLeft 0.5s ease-out var(--delay) backwards;
	}

	.skill-header {
		display: flex;
		justify-content: space-between;
		align-items: center;
		margin-bottom: 0.5rem;
	}

	.skill-name {
		font-weight: 600;
		color: var(--text-primary);
		user-select: none;
	}

	.skill-level {
		font-size: 0.85rem;
		font-weight: 700;
		color: var(--primary);
		user-select: none;
	}

	@keyframes slideInLeft {
		from {
			opacity: 0;
			transform: translateX(-20px);
		}
		to {
			opacity: 1;
			transform: translateX(0);
		}
	}
</style>
