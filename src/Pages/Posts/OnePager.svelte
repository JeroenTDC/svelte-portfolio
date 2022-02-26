<script>
    // https://github.com/doomd
    import { onMount } from "svelte";
    let box;
    let xLeft = 0;
    let xScroll = 0;
    let xWidth = 0;
    let yTop = 0;
    let yScroll = 0;
    let yHeight = 0;

    const lorem = `<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas est justo, condimentum et velit ac, euismod euismod est. Praesent urna elit, tempus vulputate nunc eu, ornare aliquet nibh. Praesent nisl lectus, viverra eu ullamcorper eu, viverra eu risus. Nullam tincidunt egestas laoreet. Integer euismod eros vel scelerisque aliquam. Phasellus sit amet velit eu elit placerat sagittis. Vivamus magna orci, vestibulum vitae dignissim eget, laoreet a mi. Curabitur cursus arcu vel odio tincidunt, eget feugiat justo lacinia.</p>`;
    const loremArray = Array(20).fill(lorem);

    function parseScroll() {
        xLeft = box.scrollLeft;
        xScroll = box.scrollWidth;
        xWidth = box.clientWidth;
        yTop = box.scrollTop;
        yHeight = box.clientHeight;
        yScroll = box.scrollHeight;
    }

    onMount(() => parseScroll());
</script>

<div
    class="box"
    bind:this={box}
    on:scroll={parseScroll}
    on:mousemove={parseScroll}
>
    {#each loremArray as paragraph}
        {@html paragraph}
    {/each}
</div>

<div class="report">
    <div>
        vertical: {yTop} from top, box is {yHeight}px high, ({yScroll} total scroll
        height)
    </div>
</div>

<style>
    .box {
        display: flex;
        flex-direction: column;
        width: 300px;
        height: 200px;
        overflow: auto;
        resize: both;
        margin-bottom: 20px;
        white-space: nowrap;
    }
</style>
