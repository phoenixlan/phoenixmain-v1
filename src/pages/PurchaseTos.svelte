<script>
    import SvelteMarkdown from 'svelte-markdown'

    import Logo from '../components/Logo.svelte';
import PageHeader from '../components/PageHeader.svelte';

    const API_URL = __myapp.env.API_URL
	const APP_HOST = __myapp.env.APP_HOST
	const APP_PROTOCOL = __myapp.env.APP_PROTOCOL
    console.log(__myapp.env)

    const fetchArticle = (async () => {
        return await (await fetch(`${API_URL}/static/tos/payment.md`)).text()
    })()
</script>

<div class="contentSimulator">
    <PageHeader><h1>Salgsbetingelser</h1></PageHeader>
    <div class="content">
        {#await fetchArticle}
        <i>Henter kjøpsvilkår</i>
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
    background-color: #111111;
    display: flex;
    justify-content: center;
    width: 100%;
}

.rules {
    width: 100%;
    max-width: 960px;
    text-align: left;
    padding: 1rem;
}
</style>