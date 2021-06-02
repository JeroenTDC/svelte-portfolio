<script>
import About from "../Pages/About/About.svelte";
import Projects from "../Pages/Projects/Projects.svelte";
import Slider from "../Pages/Slider/Slider.svelte";
import Contact from "../Pages/Contact/Contact.svelte";
import Posts from "../Pages/Posts/Posts.svelte";
import PostSvelteUnclosedElement from "../Pages/Posts/Svelte-unclosed-element.svelte";

console.log(window.location.pathname);

const pages = [{
        title: "About me",
        slug: "/about-me",
        component: About
    },
    {
        title: "Projects",
        slug: "/projects",
        component: Projects
    },
    {
        title: "Contact me",
        slug: "/contact-me",
        component: Contact
    },
    {
        title: "Posts",
        slug: "/posts",
        component: Posts,
        posts: [{
                title: "Slider",
                slug: "/posts/slider",
                component: Slider
            },
            {
                title: "Svelte unclosed element",
                slug: "/posts/unclosed",
                component: PostSvelteUnclosedElement
            },
        ]
    }
];

let selected = pages[0];

function switchPage(pageVal) {
    selected = pageVal;
    console.log(pageVal.slug);
    const nextURL = pageVal.slug;
    const nextTitle = pageVal.title;
    const nextState = {
        additionalInformation: 'Updated the URL with JS'
    };

    window.history.pushState(nextState, nextTitle, nextURL);
}
</script>

<nav>
    <div class="navTitle"><a on:click|preventDefault="{() => selected = pages[0]}" href="/"><span>happycoder.dk</span>Jeroen Stolk</a></div>
    <div class=navContents>
        <ul class="menu">
            {#each pages as page, idx}
            <li><a on:click|preventDefault="{() => switchPage(page)}" href="/">{page.title}</a></li>
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
    color: rgba(0, 0, 0, 0.8);
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
</style>
