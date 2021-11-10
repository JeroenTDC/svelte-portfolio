<script>
    const refs = [
    {
        title: "Index",
        slug: "/",
        class: "hidden"
    },
    {
        title: "Contact me",
        slug: "/contact-me",
    },
    {
        title: "Contact me",
        slug: "/contact-me",
    },
    {
        title: "Contact me",
        slug: "/contact-me",
    },
    {
        title: "Contact me",
        slug: "/contact-me",
    },
];
</script>

<main>
    <h1>Welcome</h1>
    <table>
        {#each refs as ref, idx}
        <tr>
                 <td><a href="/" target="new" class={ref.class}>{ref.title}</a></td>
                </tr>
                {/each}
    </table>
  </main>

  <style>
      table {border: 0px solid red; display: flex; flex-direction: column; }
      tr {padding: 1em; border-bottom: 1px solid rgba(255,255,255, 0.3) ;}
      tr:last-child {padding: 1em; border-bottom: 0px solid rgba(255,255,255, 0.3) ;}
  </style>