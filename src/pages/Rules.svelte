<script>
    import SvelteMarkdown from 'svelte-markdown'

    import Logo from '../components/Logo.svelte';
import PageHeader from '../components/PageHeader.svelte';

    const API_URL = __myapp.env.API_URL
	const APP_HOST = __myapp.env.APP_HOST
	const APP_PROTOCOL = __myapp.env.APP_PROTOCOL
    console.log(__myapp.env)
    
    const fetchArticles = (async () => {
        const articles = await Promise.all([
            (await fetch(`${API_URL}/static/tos/rules.md`, {
                mode: 'no-cors'
            })).text(),
            (await fetch(`${API_URL}/static/tos/payment.md`, {
                mode: 'no-cors'
            })).text(),
        ])
        return {
            rules: articles[0],
            payment: articles[1]
        }
    })()
</script>

<div class="contentSimulator">
    <PageHeader><h1>Regler og sikkerhet</h1></PageHeader>
    <div class="content">
        {#await fetchArticles}
        <i>Henter regler</i>
        {:then data}
        <div class="rules">
            <h1>Regler</h1>
            <SvelteMarkdown source={ data.rules } />

            <h1>Kjøpsvilkår</h1>
            
            <SvelteMarkdown source={ data.payment } />
        </div>
        {:catch error}
        <b>Kunne ikke hente data</b>
        {/await}
    </div>
</div>

<style>
.contentSimulator {

}

.splash {
    min-height: 30vh;
    display: flex;
    justify-content: center;
}

.splash-inner {
    margin-top: 2em;
}

.splash-inner > img {
    width: 20em;
}

.content {
    padding: 1rem;
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