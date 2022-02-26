<script>
/* import About from "../Pages/About/About.svelte";
import Projects from "../Pages/Projects/Projects.svelte"; */
import Slider from "../Pages/Slider/Slider.svelte";
import Contact from "../Pages/Contact/Contact.svelte";
import OnePager from "../Pages/Posts/OnePager.svelte";
import Index from "../Pages/Index/Index.svelte";
import Posts from "../Pages/Posts/Posts.svelte";
import PostSvelteUnclosedElement from "../Pages/Posts/Svelte-unclosed-element.svelte";
import Gsap from "../Pages/Posts/Gsap.svelte";

console.log(window.location.pathname);

const pages = [/* {
        title: "About me",
        slug: "/about-me",
        component: About
    },
    {
        title: "Projects",
        slug: "/projects",
        component: Projects
    }, */
    {
        title: "Index",
        //slug: "/",
        slug: "/",
        //component: Index,
        component: Gsap,
        class: "hidden"
    },
    {
        title: "Contact me",
        slug: "/contact-me",
        component: Contact,
    },
    {
                title: "GSAP - First try",
                slug: "/posts/gsap",
                component: Gsap
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
            {
                title: "GSAP - First try",
                slug: "/posts/gsap",
                component: Gsap
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
    <div class="navTitle"><a on:click|preventDefault="{() =>  switchPage(pages[0])}" href="/">Jeroen Stolk<span>Frontend developer</span></a></div>
    <div class=navContents>
        <ul class="menu">
            {#each pages as page, idx}
                 <li><a on:click|preventDefault="{() => switchPage(page)}" href="/" class={page.class}>{page.title}</a></li>
            {/each}
        </ul>
    </div>
</nav>

<svelte:component this="{selected.component}" />

<style>
    .hidden {
        display: none;
    }
nav {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    background-color: #333;
    background-color: #1d4eb4;
    border-bottom: 1px solid rgba(255, 255, 255, 0.2);
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
    opacity: 0.5;
}

nav .navTitle a {
    text-transform: capitalize;
    font-weight: 700;
}

nav .navTitle span::before {
    content: "|";
    margin: 0 0.5em;
    opacity: 0.55;
}

nav a {
    display: flex;
    flex-direction: row;
    color: rgba(255, 255, 255, 0.85);
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
