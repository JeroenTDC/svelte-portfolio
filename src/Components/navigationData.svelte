<script context="module">
export const pages = [{
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
</script>
