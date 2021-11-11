<script>
	async function getStackBookmarks() {
		const res = await fetch(`https://api.stackexchange.com/2.2/users/16093999/favorites?order=desc&sort=creation&site=stackoverflow`);
		const text = await res.json();

		if (res.ok) {
			return text;
		} else {
			throw new Error(text);
		}
	}
	
	let promise = getStackBookmarks();

	console.log(promise);

</script>

<div class="card">
<h2>My StackOverflow bookmarks!</h2>

{#await promise}
	<p>...waiting</p>
{:then bookmarks}
    {#each bookmarks.items as item}
         <p><a href={item.link} target="new">{item.title}</a></p>
    {/each}
{:catch error}
	<p style="color: red">{error.message}</p>
{/await}
</div>

<style>.card {flex-direction: column; border: 1px solid rgba(0,0,0,0.1); margin: 1em; padding: 2em; display: flex; }
p {margin:0.5em 0}

</style>