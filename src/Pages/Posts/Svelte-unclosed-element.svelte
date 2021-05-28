<script>
  const pages = [
    { color: "1. about" },
    { color: "2. adress" },
    { color: "3. slider" },
    { color: "4. about" },
    { color: "5. adress" },
    { color: "6. slider" },
    { color: "7. about" },
    { color: "8. adress" },
    { color: "9. slider" },
    { color: "10. about" },
    { color: "11. adress" },
    { color: "12. slider" },
    { color: "13. about" },
    { color: "14. adress" },
    { color: "15. slider" },
    { color: "16. about" },
    { color: "17. adress" },
    { color: "18. slider" },
    { color: "19. about" },
    { color: "20. adress" },
    { color: "21. slider" },
  ];

  let divStartSpecial = '<div style="color:red">';
  let divStart = '<div>';
  let divEnd = '</div>';
</script>

<div class="divs">
{#each pages as page, index} {#if index % 10 === 9} {@html divStartSpecial + page.color}{:else} {@html divStart} {/if} {page.color}
{#if index % 10 === 0}{@html divEnd} {/if} {/each}
</div>

<div style="display:none">
<div class="new-div">dummy</div>
</div>
<style>
  .new-div {
    color: red;
  }
  .divs {display: flex;  flex-direction: column;}
</style>