<script lang="ts">
	import CV from './components/CV.svelte';
  	export let name: string = 'world';
</script>

<main>
	<CV />
</main>

<style>
	:global(*) {
		margin: 0;
		padding: 0;
		box-sizing: border-box;
	}

	h1 {
		color: #ff3e00;
		font-size: 2em;
	}

	p {
		color: #333;
	}
</style>