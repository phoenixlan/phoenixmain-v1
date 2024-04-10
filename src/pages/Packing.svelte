<script>
import PageHeader from '../components/PageHeader.svelte';

const legal = [
    "Datamaskin(eller spillkonsoll) med alt tilbehør",
    "Nettverkskabel med en minumumslengde på 10 meter. Vi har ikke trådløst nett for deltakere.",
    "Strømpad/strømforgrener, det er beregnet et strømuttak per person.",
    "Tannbørste og andre hygieneartikler.",
    "Penger.",
    "Vann eller brus. Eventuelt lukkbar vannflaske.",
    "Eventuelle medisiner hvis man trenger det (Ta kontakt med crew hvis det er noe vi bør vite).",
    "Din billett",
    "Sovepos/dyne og liggeunderlag/luftmadrass",
    "Gyldig legitimasjon. (Pass, bankkort med bilde, førerkort). Studentkort er ikke gyldig legitimasjon."
];
// TODO re-add foreldreattest later
const illegal = [
    "Alkohol eller andre rusmidler.",
    "Høytalere.",
    "Hvitevarer."
];
</script>

<div class="contentSimulator">
    <PageHeader><h1>Pakkeliste</h1></PageHeader>
    <div class="content">
        <div class="content-inner">
            <h1>Hva burde jeg ta med?</h1>
            <ul>
                {#each legal as item}
                    <li>{item}</li>
                {/each}
            </ul>
            <h1>Hva kan jeg <b>IKKE</b> ta med?</h1>
            <ul>
                {#each illegal as item}
                    <li>{item}</li>
                {/each}
            </ul>
        </div>
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
}

.content-inner {
    width: 100%;
    max-width: 960px;
    text-align: left;
}
</style>
