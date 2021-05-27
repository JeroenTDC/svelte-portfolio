<script>
  //import data from "./items.json";
  import About from "../Pages/About/About.svelte";
  import Address from "../Pages/Address/Address.svelte";

  let data = {
    pages: [
      {
        title: "About us",
        path: "About",
      },
      {
        title: "Our address",
        path: "Address",
      },
    ],
  };

  let renderedPage = Address;

  function selectPage() {
    renderedPage === Address ? About : Address;
  }
</script>

<div>
  {#each data.pages as page}
  <button on:click="{selectPage}">{page.path}</button>
  {/each}
</div>

<svelte:component this="{renderedPage}" />
