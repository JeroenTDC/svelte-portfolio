<script>
    const refs = [
    {
        title: "Licenses pretotype 1/3",
        slug: "https://svelte.dev/repl/db7f878242814d109cc17514ab9a8fd3",
    },
    {
        title: "Licenses pretotype 2/3 -> Z-index trickery",
        slug: "https://svelte.dev/repl/7aed593a9b324ab9af571643f7a7fead",
    },
    {
        title: "Licenses pretotype 3/3 -> Z-index trickery",
        slug: "https://svelte.dev/repl/9729b3e49719491b8565e6ec16b90156",
    },
    {
        title: "Onboarding - popover - features - v5 - 1/2",
        slug: "https://svelte.dev/repl/f95e7f24a8f24ceea1557ac36e85e040",
    },
    {
        title: "Onboarding - popover - features - v5 - 2/2",
        slug: "https://svelte.dev/repl/46dbfb187bc14d96b0583fc720f24bfc",
    },
    {
        title: "Create input rows -> UX prototype",
        slug: "https://svelte.dev/repl/c1f4c6fddbad4c6780a46982eef6d0fb",
    },
    {
        title: "TDC order confirmation -> UX/UI suggestion",
        slug: "https://svelte.dev/repl/b712fbbe6aed4f3bad2c0089165357b2",
    },
];
const gimmicks = [
    {
        title: "Theme switch and toggle with button component",
        slug: "https://svelte.dev/repl/0eb6b2e0f7b24e5882aae2b37319a398",
        /* class: "hidden" */
    },
    {
        title: "Regex tester",
        slug: "https://svelte.dev/repl/1724b67a82f24df8ae74d3b9e5c3be2c",
    },
    {
        title: "Roll the dice! -> turns at meetings",
        slug: "https://svelte.dev/repl/913aeb4c3e4547bb926f56db5b3cac0c",
    },
    {
        title: "Calculated input placeholder",
        slug: "https://svelte.dev/repl/f84ca840a4104e7fa8d3387ac97ffd14",
    },
    {
        title: "Px vs Em",
        slug: "https://svelte.dev/repl/6e38b56bc6994f53b0f2753fd53eba78",
    },
    {
        title: "Counter + stored actions -> Minimal code",
        slug: "https://svelte.dev/repl/aaa880a9a17441d2bb95bfda56036da2",
    },
];
</script>

<main>
    <h1>Welcome</h1>
    <h2>UX/UI</h2>

    <table>
        {#each refs as ref, idx}
        <tr>
                 <td><a href={ref.slug} target="new" class={ref.class}>{ref.title}</a></td>
                </tr>
                {/each}
    </table>
    <h2>Gimmicks</h2>

    <table>
        {#each gimmicks as ref, idx}
        <tr>
                 <td><a href={ref.slug} target="new" class={ref.class}>{ref.title}</a></td>
                </tr>
                {/each}
    </table>
  </main>

  <style>
      table {border: 0px solid red; display: flex; flex-direction: column; }
      tr {padding: 1em; border-bottom: 1px solid rgba(255,255,255, 0.3) ;}
      tr:last-child {padding: 1em; border-bottom: 0px solid rgba(255,255,255, 0.3) ;}
  </style>