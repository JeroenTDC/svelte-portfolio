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

const iframeWidth = tweened(300, {
    duration: 800,
    easing: backInOut
});
const iframeHeight = tweened(600, {
    duration: 800,
    easing: backInOut
});

function toggleIframeSize() {
    $iframeWidth === 300 ? iframeWidth.set(600) : iframeWidth.set(300);
    $iframeHeight === 600 ? iframeHeight.set(300) : iframeHeight.set(600);
}

function autoToggleIframeSize() {
    setTimeout(function() {
        $iframeWidth === 300 ? iframeWidth.set(600) : iframeWidth.set(300);
        $iframeHeight === 600 ? iframeHeight.set(300) : iframeHeight.set(600);
    }, 2000);
    setTimeout(autoToggleIframeSize, 4000);
}

setTimeout(autoToggleIframeSize, 2000);


</script>

<button on:click={toggleIframeSize}>Toggle</button>

<iframe src="http://www.svelte.dev" frameborder="0" title="iframe" style="width: {$iframeWidth}px; height: {$iframeHeight}px;"/>

<style>
iframe {
    display: flex;
}
</style>
