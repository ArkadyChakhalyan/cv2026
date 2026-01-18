<script>
	const contacts = [
		{ icon: '📧', label: 'Email', value: 'arkadychakhalyan@gmail.com', link: 'mailto:arkadychakhalyan@gmail.com' },
		{ icon: '📱', label: 'Телефон', value: '+7 (999) 667-16-88', link: 'tel:+79996671688' },
		{ icon: '💬', label: 'Telegram', value: '@ArkadyCh', link: 'https://t.me/ArkadyCh' },
		{ icon: '💼', label: 'HeadHunter', value: 'Аркадий Чахалян', link: 'https://hh.ru/resume/fa68ca89ff096650430039ed1f6e5865705364' },
		{ icon: '🐙', label: 'GitHub', value: 'ArkadyChakhalyan', link: 'https://github.com/ArkadyChakhalyan' },
	];
</script>

<div class="contact-section">
	<h2>Контакты и ссылки</h2>

	<div class="contact-links">
		{#each contacts as contact, index (index)}
			<a href={contact.link} target="_blank" class="contact-item" style="--delay: {index * 0.05}s">
				<span class="contact-icon">{contact.icon}</span>
				<div class="contact-text">
					<p class="contact-label">{contact.label}</p>
					<p class="contact-value">{contact.value}</p>
				</div>
			</a>
		{/each}
	</div>
</div>

<style>
	.contact-section {
		padding: 1rem 0;
		background: var(--glass-bg);
		border: 1px solid var(--border-color);
		border-radius: 12px;
		padding: 2rem;
	}

	h2 {
		font-size: 2rem;
		margin-bottom: 2rem;
		background: linear-gradient(135deg, var(--primary) 0%, var(--accent) 100%);
		-webkit-background-clip: text;
		-webkit-text-fill-color: transparent;
		background-clip: text;
	}

	.contact-grid {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
		gap: 2rem;
	}

	h3 {
		margin-top: 0;
		margin-bottom: 1.5rem;
		font-size: 1.3rem;
		color: var(--accent);
	}

	.contact-links {
		display: flex;
		flex-direction: column;
		gap: 1rem;
	}

	.contact-item {
		display: flex;
		gap: 1rem;
		padding: 1rem;
		background: rgba(99, 102, 241, 0.05);
		border: 1px solid var(--border-color);
		border-radius: 8px;
		text-decoration: none;
		color: inherit;
		transition: all 0.3s ease;
		animation: slideInLeft 0.5s ease-out var(--delay) backwards;
	}

	.contact-item:hover {
		background: rgba(99, 102, 241, 0.1);
		border-color: var(--primary);
		transform: translateX(8px);
	}

	.contact-icon {
		font-size: 1.5rem;
		flex-shrink: 0;
	}

	.contact-text {
		display: flex;
		flex-direction: column;
		overflow: hidden;
	}

	.contact-label {
		margin: 0;
		font-size: 0.85rem;
		color: var(--text-secondary);
		font-weight: 600;
	}

	.contact-value {
		margin: 0.25rem 0 0 0;
		color: var(--text-primary);
		font-weight: 600;
		overflow: hidden;
		text-overflow: ellipsis;
		white-space: nowrap;
		max-width: 100%;
	}

	.form-group {
		margin-bottom: 1.2rem;
	}

	.form-input {
		width: 100%;
		padding: 0.75rem;
		background: rgba(99, 102, 241, 0.05);
		border: 1px solid var(--border-color);
		border-radius: 8px;
		color: var(--text-primary);
		font-size: 1rem;
		font-family: inherit;
		transition: all 0.3s ease;
		box-sizing: border-box;
	}

	.form-input::placeholder {
		color: var(--text-secondary);
		opacity: 0.7;
	}

	.form-input:focus {
		outline: none;
		background: rgba(99, 102, 241, 0.1);
		border-color: var(--primary);
		box-shadow: 0 0 0 3px rgba(99, 102, 241, 0.1);
	}

	textarea.form-input {
		resize: vertical;
		min-height: 120px;
	}

	.submit-button {
		width: 100%;
		padding: 0.85rem;
		background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
		border: none;
		border-radius: 8px;
		color: white;
		font-weight: 600;
		font-size: 1rem;
		cursor: pointer;
		transition: all 0.3s ease;
		box-shadow: 0 5px 20px rgba(99, 102, 241, 0.3);
	}

	.submit-button:hover {
		transform: translateY(-2px);
		box-shadow: 0 8px 30px rgba(99, 102, 241, 0.4);
	}

	.submit-button:active {
		transform: translateY(0);
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
