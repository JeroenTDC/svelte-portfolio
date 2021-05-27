<script>
  import About from "../Pages/About/About.svelte";
  import Address from "../Pages/Address/Address.svelte";
  import Slider from "../Pages/Slider/Slider.svelte";

  const pages = [
    { color: "about", component: About },
    { color: "adress", component: Address },
    { color: "slider", component: Slider },
  ];

  let selected = pages[0];
</script>

<nav>
  {#each pages as page}
  <a on:click="{() => selected = page}" href="#">{page.color}</a>
  {/each}
</nav>

<svelte:component this="{selected.component}" />
