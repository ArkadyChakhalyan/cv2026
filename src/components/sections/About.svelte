<script>
	import AnimatedCard from '../AnimatedCard.svelte';
</script>

<div class="about-section">
	<div class="about-content">
			<h2>Обо мне</h2>
			<p>
				Привет! Я Senior Frontend-разработчик с сильным дизайнерским бэкграундом и большим коммерческим опытом. Специализируюсь на разработке сложных интерфейсов, проектировании архитектуры фронтенда и построении UI-систем.
			</p>
			<div class="highlights">
				<div class="highlight-item">
					<span class="number">5+</span>
					<span class="text">Лет коммерческого опыта</span>
				</div>
				<div class="highlight-item">
					<span class="number">6</span>
					<span class="text">Завершенный проектов</span>
				</div>
				<div class="highlight-item">
					<span class="number">1</span>
					<span class="text">Успешный <a target="_blank" href="https://cashbackcheck.netlify.app/">Pet Project</a></span>
					</div>
			</div>
			<p class="description">
				Последние 4+ лет развиваю таск-менеджер Kanbanchi: принимаю ключевые технические решения, оптимизирую производительность, внедряю фичи и менторю команду.
				<br />
				<br />
				Моя сила — делать фронтенд быстрым, масштабируемым и предсказуемым, с переиспользуемыми компонентами и UI-библиотеками, при этом не забывая про UX/UI и детали, которые делают продукт «любимчиком пользователей».
			</p>
	</div>
</div>

<style>
	.about-section {
		background: var(--glass-bg);
		border: 1px solid var(--border-color);
		border-radius: 12px;
	}

	.about-content {
		padding: 2rem;
	}

	h2 {
		font-size: 2rem;
		margin-top: 0;
		margin-bottom: 1.5rem;
		background: linear-gradient(135deg, var(--primary) 0%, var(--accent) 100%);
		-webkit-background-clip: text;
		-webkit-text-fill-color: transparent;
		background-clip: text;
	}

	p {
		font-size: 1.1rem;
		line-height: 1.8;
		color: var(--text-secondary);
		margin: 0 0 1.5rem 0;
	}

	.highlights {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
		gap: 1rem;
		margin: 2rem 0;
		padding: 2rem 0;
		border-top: 1px solid var(--border-color);
		border-bottom: 1px solid var(--border-color);
	}

	.highlight-item {
		display: flex;
		flex-direction: column;
		align-items: center;
		gap: 0.5rem;
	}

	.number {
		font-size: 2.5rem;
		font-weight: 700;
		background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
		-webkit-background-clip: text;
		-webkit-text-fill-color: transparent;
		background-clip: text;
	}

	.text {
		font-size: 0.9rem;
		color: var(--text-secondary);
		text-align: center;
	}

	.description {
		margin-top: 1.5rem;
	}
</style>
