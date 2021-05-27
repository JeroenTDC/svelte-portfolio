<script>
  import About from "../Pages/About/About.svelte";
  import Address from "../Pages/Address/Address.svelte";

  const pages = [
    { color: "about", component: About },
    { color: "adress", component: Address },
  ];

  let selected = pages[0];
</script>

{#each pages as page}
<a on:click="{() => selected = page}" href="#">{page.color}</a>
{/each}

<svelte:component this="{selected.component}" />
