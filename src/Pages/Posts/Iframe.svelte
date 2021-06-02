<script>
import {
    writable
} from 'svelte/store';
import {
    tweened
} from 'svelte/motion';
import {
    backInOut
} from 'svelte/easing';
import Menu from './Menu.svelte';

const iframeWidth = tweened(50, {
    duration: 800,
    easing: backInOut
});
const iframeHeight = tweened(600, {
    duration: 800,
    easing: backInOut
});

function toggleIframeSize() {
    $iframeWidth === 50 ? iframeWidth.set(100) : iframeWidth.set(500);
    $iframeHeight === 600 ? iframeHeight.set(300) : iframeHeight.set(600);
}

function autoToggleIframeSize() {
    setTimeout(function() {
        $iframeWidth === 50 ? iframeWidth.set(100) : iframeWidth.set(50);
        $iframeHeight === 600 ? iframeHeight.set(300) : iframeHeight.set(600);
    }, 2000);
    setTimeout(autoToggleIframeSize, 4000);
}

setTimeout(autoToggleIframeSize, 2000);


</script>

<button on:click={toggleIframeSize}>Toggle</button>
<div class="iframe">
<iframe src="https://www.nettalk.dk/kundeservice/service.asp" scrolling="no" frameborder="0" title="iframe" style="width: {$iframeWidth}%; height: {$iframeHeight}px;"/>
</div>
<style>
iframe {
    display: flex;
}
.iframe {padding: 3em; background-color: rgba(0,0,0,0.1);}
</style>
