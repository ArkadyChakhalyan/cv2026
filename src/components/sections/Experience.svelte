<script>
	import AnimatedCard from '../AnimatedCard.svelte';

	const experiences = [
		{
			title: 'Lead Frontend Developer',
			company: 'Kanbanchi',
			period: 'Август 2024 - Сейчас',
			description:
				'Разработка и развитие таск-менеджера <a target="_blank" href="https://kanbanchi.com">Kanbanchi</a> (3M+ установок, рейтинг 4.7/5).<br /><br />Достижения:<br /><br />- Реализовал новый онбординг для новых пользователей, что привело к росту конверсии в подписку на 20%, за счет оптимизации пользовательских сценариев и внедрения персонализированных элементов интерфейса<br /><br />- Достиг повышения интеграционной гибкости продукта, измеряемого ростом количества внешних подключений на ~25%, реализовав микросервис для создания вебхуков и интеграции с сервисом для автоматизаций Make.com<br /><br />- Достиг ускорения загрузки приложения до максимальных показателей Lighthouse, что обеспечило моментальную загрузку и подготовку к публикации в Google Play, за счет уменьшения login-bundle, оптимизации кода и ресурсов фронтенда',
			tags: ['TypeScript', 'React', 'Redux', 'SCSS', 'WebSocket', 'REST API', 'Webpack', 'Java']
		},
		{
			title: 'Middle Frontend Developer',
			company: 'LangMagic',
			period: 'Август 2022 - Август 2024',
			description:
				'Разрабатывал веб-приложение <a target="_blank" href="https://langmagic.com">LangMagic</a> для изучения языков через YouTube с использованием возможностей AI (ChatGPT).<br /><br />Достижения:<br /><br />- Разработал и внедрил фронтенд-архитектуру с нуля, обеспечив масштабируемость и удобство поддержки приложения<br /><br />- Создал UI-библиотеку компонентов, использованную по всему проекту, что ускорило разработку новых функциональных блоков<br /><br />- Интегрировал приложение с backend Rest API и сервисами AI (ChatGPT API), реализовав сложные пользовательские сценарии<br /><br />- Внедрил дизайн-концепции и макеты Figma, обеспечив последовательный и современный UX/UI',
			tags: ['TypeScript', 'React', 'Redux', 'MaterialUI', 'React Router', 'Webpack', 'REST API', 'ChatGPT API']
		},
		{
			title: 'Middle Frontend Developer',
			company: 'Kanbanchi',
			period: 'Июнь 2022 - Август 2024',
			description:
				'Разработка и развитие таск-менеджера <a target="_blank" href="https://kanbanchi.com">Kanbanchi</a> (3M+ установок, рейтинг 4.7/5).<br /><br />Достижения:<br /><br />- Перевел ключевые легаси-модули с JavaScript, Backbone и jQuery на TypeScript, React и Redux, обеспечив лучшую масштабируемость и переиспользуемость компонентов<br /><br />- Достиг заметного улучшения производительности интерфейса, измеряемого сокращением количества лишних ререндеров на ~30%, за счёт анализа рендеринга компонентов и внедрения оптимизаций на уровне архитектуры компонентов<br /><br />- Достиг заметного ускорения работы приложения на больших досках, измеряемого ростом производительности при работе с сотнями карточек и списков, за счет оптимизации рендеринга и внедрения виртуальных листов<br /><br />- Провел редизайн ключевых пользовательских сценариев, сократив количество шагов в них на ~30%',
			tags: ['TypeScript', 'React', 'Redux', 'Backbone', 'jQuery', 'SCSS', 'REST API']
		},
		{
			title: 'Junior Frontend Developer',
			company: 'Kanbanchi',
			period: 'Нобярь 2020 - Июнь 2022',
			description:
				'Разработка и развитие таск-менеджера <a target="_blank" href="https://kanbanchi.com">Kanbanchi</a> (3M+ установок, рейтинг 4.7/5).<br /><br />Достижения:<br /><br />- Участвовал в устранении ошибок в приложении, повышая качество и надежность функциональности<br /><br />- Реализовал новые функции по аналогии с продуктами конкурентов (Trello, Jira, Monday, ClickUp), чтобы удерживать пользователей и соответствовать современным требованиям рынка, что способствовало росту пользовательской активности',
			tags: ['TypeScript', 'React', 'Redux', 'Backbone', 'jQuery', 'SCSS', 'REST API']
		}
	];
</script>

<div class="experience-section">
	<h2>Опыт работы</h2>
	<div class="timeline">
		{#each experiences as exp, index (index)}
			<AnimatedCard delay={index * 0.1}>
				<div class="timeline-item">
					<div class="timeline-marker" />
					<div class="experience-card">
						<div class="card-header">
							<h3>{exp.title}</h3>
							<span class="period">{exp.period}</span>
						</div>
						<p class="company">{exp.company}</p>
						<p class="description" >{@html exp.description}</p>
						<div class="tags">
							{#each exp.tags as tag}
								<span class="tag">{tag}</span>
							{/each}
						</div>
					</div>
				</div>
			</AnimatedCard>
		{/each}
	</div>
</div>

<style>
	.experience-section {
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

	.timeline {
		position: relative;
		padding-left: 2rem;
	}

	.timeline::before {
		content: '';
		position: absolute;
		left: 4px;
		top: 0;
		bottom: 0;
		width: 2px;
		background: linear-gradient(180deg, var(--primary) 0%, var(--accent) 100%);
		opacity: 0.3;
	}

	.timeline-item {
		position: relative;
		margin-bottom: 2rem;
	}

	.timeline-marker {
		position: absolute;
		left: -2.5rem;
		top: 1.5rem;
		width: 1.5rem;
		height: 1.5rem;
		border-radius: 50%;
		background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
		border: 3px solid var(--bg-dark);
		box-shadow: 0 0 0 4px var(--primary);
	}

	.experience-card {
		background: var(--glass-bg);
		border: 1px solid var(--border-color);
		border-radius: 12px;
		padding: 1.5rem;
		backdrop-filter: blur(10px);
		transition: all 0.3s ease;
	}

	.experience-card:hover {
		border-color: var(--primary);
		box-shadow: 0 10px 30px rgba(99, 102, 241, 0.2);
		transform: translateX(8px);
	}

	.card-header {
		display: flex;
		justify-content: space-between;
		align-items: flex-start;
		gap: 1rem;
		margin-bottom: 0.5rem;
	}

	h3 {
		margin: 0;
		font-size: 1.3rem;
		color: var(--text-primary);
	}

	.period {
		font-size: 0.85rem;
		color: var(--primary);
		font-weight: 600;
		white-space: nowrap;
	}

	.company {
		margin: 0.5rem 0 1rem 0;
		color: var(--accent);
		font-weight: 600;
	}

	.description {
		margin: 1rem 0;
		color: var(--text-secondary);
		line-height: 1.6;
	}

	.tags {
		display: flex;
		flex-wrap: wrap;
		gap: 0.5rem;
		margin-top: 1.2rem;
	}

	.tag {
		display: inline-block;
		padding: 0.4rem 0.8rem;
		background: rgba(99, 102, 241, 0.1);
		border: 1px solid var(--primary);
		border-radius: 20px;
		font-size: 0.8rem;
		color: var(--primary);
		transition: all 0.3s ease;
		user-select: none;
	}

	.tag:hover {
		background: var(--primary);
		color: var(--bg-dark);
	}
</style>
