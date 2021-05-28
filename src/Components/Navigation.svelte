<script>
  import About from "../Pages/About/About.svelte";
  import Projects from "../Pages/Projects/Projects.svelte";
  import Slider from "../Pages/Slider/Slider.svelte";
  import Contact from "../Pages/Contact/Contact.svelte";
  import Posts from "../Pages/Posts/Posts.svelte";
  import PostSvelteUnclosedElement from "../Pages/Posts/Svelte-unclosed-element.svelte";

  const pages = [
    { title: "About me", component: About },
    { title: "Projects", component: Projects },
    { title: "Contact me", component: Contact },
    { title: "Posts", component: Posts, posts: [
      { title: "Slider", component: Slider },
      { title: "Svelte unclosed element", component: PostSvelteUnclosedElement },
    ]}
  ];

  let selected = pages[0];
</script>

<nav>
  <div class="navTitle"><a on:click|preventDefault="{() => selected = pages[0]}" href="/"><span>happycoder.dk</span>Jeroen Stolk</a></div>
  <div class=navContents>
    <ul class="menu">
  {#each pages as page}
    <li><a on:click|preventDefault="{() => selected = page}" href="/">{page.title}</a>
      {#if page.posts}
        <ul class="subMenu">
          {#each page.posts as post}
            <li><a on:click|preventDefault="{() => selected = post}" href="/">{post.title}</a></li>
          {/each}
        </ul>
      {/if}
    </li>
  {/each}
</ul>
</div>
</nav>

<svelte:component this="{selected.component}" />

<style>

  nav {display: flex; flex-direction: row; justify-content: space-between; background-color: #333; color: #fff;}
  nav .navTitle, nav .navContents {border: 0px solid red; }
  nav .navContents {display: flex; flex-direction: row;}
  nav .navTitle span {text-transform: none; font-weight: normal;}
  nav .navTitle span::after {content: "|"; margin: 0 0.5em;opacity: 0.65;}
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
.menu {display: flex; flex-direction: row; list-style: none; padding: 0; margin: 0;}
.menu li {position: relative;}
.subMenu {background-color: rgba(0,0,0,0.65); box-shadow: 1px 1px 8px rgba(0,0,0,0.2); position: absolute; color: red; right:0; list-style: none; padding: 0; margin: 0; width:max-content; }
.subMenu a, .subMenu a:hover {font-size: 1.6rem;opacity: 0.65;}
.subMenu a:hover {opacity: 1}
</style>