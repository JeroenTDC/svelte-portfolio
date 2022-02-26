<script>
    import { onMount } from "svelte";

    let getSections = [];

    /* function myFunction() {
        console.log("scrolling");
    } */

    onMount(() => {
        document.onscroll = function () {
            myFunction();
        };
        getSections = document.querySelectorAll("section");
        console.log(getSections);

        function myFunction() {
            getSections.forEach(function (itemSection, index) {
                console.log(itemSection, index);
                console.log(itemSection.scrollLeft);
            });
        }
    });
    /* 
    scroller.addEventListener("scroll", (event) => {
        output.textContent = `scrollTop: ${scroller.scrollTop}`;
    }); */

    let sections = [
        { class: "red", text: "finish Svelte tutorial" },
        { class: "blue", text: "build an app" },
        { class: "green", text: "world domination" },
    ];
</script>

<div id="scroller">
    {#each sections as section}
        <section class={section.class}>
            <h1>{section.text}</h1>
            <p>Scrolltop: {this.scrollTop}</p>
        </section>
    {/each}
</div>

<style>
    section {
        height: 100vh;
    }

    h1 {color: #000}

    .yellow {
        background-color: lightyellow;
    }
    .red {
        background-color: lightcoral;
    }
    .blue {
        background-color: lightblue;
    }
    .green {
        background-color: lightgreen;
    }
</style>
