<script>
	import Navigation from './Components/Navigation.svelte';
	export let name;
</script>

<Navigation/>

<style>
	:global(nav, nav a, nav a:hover) {
		display: flex;
		flex-direction: row;
		justify-content: space-around;
		font-size: 1.6rem;
		color:rgba(0,0,0,0.45);
		font-weight: 700;
		text-decoration: none;
		padding: 0.5em;
	}

	:global(main) {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	:global(h1) {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>