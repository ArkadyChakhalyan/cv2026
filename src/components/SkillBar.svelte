<script>
	export let level = 0;
</script>

<div class="skill-bar">
	<div class="skill-fill" style="--level: {level}%" />
</div>

<style>
	.skill-bar {
		width: 100%;
		height: 6px;
		background: rgba(99, 102, 241, 0.1);
		border-radius: 10px;
		overflow: hidden;
		border: 1px solid var(--border-color);
	}

	.skill-fill {
		height: 100%;
		width: var(--level);
		background: linear-gradient(90deg, var(--primary) 0%, var(--accent) 100%);
		border-radius: 10px;
		animation: fillSkill 1s ease-out forwards;
		box-shadow: 0 0 10px rgba(99, 102, 241, 0.5);
	}

	@keyframes fillSkill {
		from {
			width: 0;
			opacity: 0;
		}
		to {
			width: var(--level);
			opacity: 1;
		}
	}
</style>
