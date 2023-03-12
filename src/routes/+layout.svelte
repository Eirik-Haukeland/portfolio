<script>
  import './main.css';
  import Header from '../components/Header.svelte';
</script>

<a class="hideMe" href="#content">skip to content</a>

<Header />

<main id="content">
    <slot/>
</main>

<style>
    main {
        padding-block: 2em;
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 1.5em;
    }

    .hideMe {
        position: absolute;
        left: -500px;
    }
</style>
