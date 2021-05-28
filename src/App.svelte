<script>
	import Navigation from './Components/Navigation.svelte';
</script>

<svelte:head>
	<link rel="stylesheet" href="/style.css">
</svelte:head>

<Navigation/>

<style>


	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>