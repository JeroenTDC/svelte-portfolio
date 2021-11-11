<script>
import Navigation from './Components/Navigation.svelte';
</script>

<svelte:head>
    <link rel="stylesheet" href="/style.css">
    </svelte:head>

    <Navigation/>
    <footer>
        <a href="https://github.com/JeroenTDC/svelte-portfolio">Portfolio Github repository</a>
    </footer>

<style>
@media (min-width: 640px) {
    main {
        max-width: none;
    }
    footer {clear: both; display: flex; border-top:1px solid rgba(255,255,255,0.15); justify-content: center; margin: 5em 0; padding-top: 2em;}
}
</style>
