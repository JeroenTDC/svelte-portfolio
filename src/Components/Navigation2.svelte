<script>
  import About from "../Pages/About/About.svelte";
  import Address from "../Pages/Address/Address.svelte";

  const pages = [
    { color: "about", component: About },
    { color: "adress", component: Address },
  ];

  let selected = pages[0];
</script>

<!-- <select bind:value={selected}>
	{#each options as option}
		<option value={option}>{option.color}</option>
	{/each}
</select> -->

{#each pages as page}
<a on:click="{() => selected = page}" href="#">{page.color}</a>
{/each}

<svelte:component this="{selected.component}" />
