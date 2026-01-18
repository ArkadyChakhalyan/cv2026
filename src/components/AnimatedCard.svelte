<script>
	export let delay = 0;
</script>

<div class="animated-card" style="--animation-delay: {delay}s">
	<slot />
</div>

<style>
	.animated-card {
		backdrop-filter: blur(10px);
		animation: fadeInUp 0.6s ease-out var(--animation-delay) backwards;
	}

	@keyframes fadeInUp {
		from {
			opacity: 0;
			transform: translateY(20px);
		}
		to {
			opacity: 1;
			transform: translateY(0);
		}
	}
</style>
