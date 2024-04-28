<script>
    import SvelteMarkdown from 'svelte-markdown'
    import { Moon } from 'svelte-loading-spinners';
    import { Link } from 'svelte-routing';

    import PageHeader from '../components/PageHeader.svelte';

    const API_URL = __myapp.env.API_URL
	const APP_HOST = __myapp.env.APP_HOST
	const APP_PROTOCOL = __myapp.env.APP_PROTOCOL
    console.log(__myapp.env)

    const fetchArticle = (async () => {
        return await (await fetch(`${API_URL}/static/tos/rules.md`)).text()
    })()
</script>

<div class="contentSimulator">
    <PageHeader><h1>Regler og sikkerhet</h1></PageHeader>
    <div class="content">
        <p>Du kan også lese våre salgsbetingelser <Link to="/salgsbetingelser">her</Link></p>
        {#await fetchArticle}
            <Moon color="#FF4B9D"/>
        {:then data}
        <div class="rules">
            <SvelteMarkdown source={ data } />
        </div>
        {:catch error}
        <b>Kunne ikke hente data</b>
        {/await}
    </div>
</div>

<style>

.content {
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: #111111;
    width: 100%;
}

.rules {
    width: 100%;
    max-width: 960px;
    text-align: left;
    padding: 1rem;
}
</style>