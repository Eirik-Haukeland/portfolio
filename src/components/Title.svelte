<script >
  export let pageTitle = "title"
  export let hidden = false
</script>

<svelte:head>
    <title>EBH portfolio | {pageTitle}</title>
</svelte:head>

<h1 hidden={hidden}>{pageTitle}</h1>

<style>
    h1 {
        font-family: var(--main-font);
    }

    @media screen and (max-width: 700px) {
        h1 {
            text-align: center;
        }
    }
</style>