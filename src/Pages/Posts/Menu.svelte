<script>
import About from "../Pages/About/About.svelte";
import Projects from "../Pages/Projects/Projects.svelte";
import Slider from "../Pages/Slider/Slider.svelte";
import Contact from "../Pages/Contact/Contact.svelte";
import Posts from "../Pages/Posts/Posts.svelte";
import PostSvelteUnclosedElement from "../Pages/Posts/Svelte-unclosed-element.svelte";

const pages = [{
        title: "About me",
        component: About
    },
    {
        title: "Projects",
        component: Projects
    },
    {
        title: "Contact me",
        component: Contact
    },
    {
        title: "Posts",
        component: Posts,
        posts: [{
                title: "Slider",
                component: Slider
            },
            {
                title: "Svelte unclosed element",
                component: PostSvelteUnclosedElement
            },
        ]
    }
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
nav {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    background-color: #333;
    background-color: #fff;
    border-bottom: 1px solid #e2e2e2;
    z-index: 1;
}

nav .navTitle,
nav .navContents {
    border: 0px solid red;
}

nav .navContents {
    display: flex;
    flex-direction: row;
}

nav .navTitle span {
    text-transform: none;
    font-weight: normal;
}
nav .navTitle a {
    text-transform: capitalize;
    font-weight: 700;
}

nav .navTitle span::after {
    content: "|";
    margin: 0 0.5em;
    opacity: 0.65;
}

nav a {
    display: flex;
    flex-direction: row;
    color: rgba(0,0,0,0.8);
    text-decoration: none;
    padding: 1.5em;
    font-weight: 700;
}

.menu {
    display: flex;
    flex-direction: row;
    list-style: none;
}

.menu li {
    position: relative;
}

.subMenu {
    box-shadow: 1px 1px 8px rgba(0, 0, 0, 0.1);
    position: absolute;
    right: 0;
    list-style: none;
    width: max-content;
    border-bottom: 1px solid rgba(0,0,0,0.1);
    border-left: 1px solid rgba(0,0,0,0.1);
    padding:0.5em;
    z-index: 1;
}

.subMenu a,
.subMenu a:hover {
    opacity: 0.85;
    padding: 1em;
    font-size: 1.4rem;
}

.subMenu a:hover {
    opacity: 1
}
</style>
