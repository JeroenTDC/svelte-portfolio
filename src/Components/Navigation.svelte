<script>
  import About from "../Pages/About/About.svelte";
  import Address from "../Pages/Address/Address.svelte";
  import Slider from "../Pages/Slider/Slider.svelte";
  import PostSvelteUnclosedElement from "../Pages/Posts/Svelte-unclosed-element.svelte";

  const pages = [
    { color: "about", component: About },
    { color: "adress", component: Address },
    { color: "slider", component: Slider },
    { color: "Svelte unclosed element", component: PostSvelteUnclosedElement },
  ];

  let selected = pages[0];
</script>

<nav>
  <div class="navTitle"><span>happycoder.dk</span>Jeroen Stolk</div>
  <div class=navContents>
  {#each pages as page}
  <a on:click|preventDefault="{() => selected = page}" href="/">{page.color}</a>
  {/each}
</div>
</nav>

<svelte:component this="{selected.component}" />

<style>

  nav {display: flex; flex-direction: row; justify-content: space-between; background-color: #333; color: #fff;}
  nav .navTitle, nav .navContents {border: 0px solid red; }
  nav .navContents {display: flex; flex-direction: row;}
  nav .navTitle span {text-transform: none; font-weight: normal;}
  nav .navTitle,
  nav a,
nav a:hover {
  display: flex;
  flex-direction: row;
  font-size: 1.8rem;
  color: rgba(0, 0, 0, 0.45);
  font-weight: 700;
  text-decoration: none;
  padding: 1em;
  color:#fff;
  text-transform: capitalize;
}
</style>