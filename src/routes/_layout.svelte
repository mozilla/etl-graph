<script>
    import Nav from "../components/Nav.svelte";
    export let segment;
</script>

<style>
    main {
        width: 900px;
        padding: 2em;
        margin: 0 auto;
    }
</style>

<svelte:head>
    <title>BigQuery ETL Query Network</title>
</svelte:head>

<main>
    <h1>BigQuery ETL Query Network</h1>
    <i>Created 2020-06-18. Updated 2021-01-14 </i>
    <Nav {segment} />
    <slot />
</main>
