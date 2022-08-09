<script>
    import Logo from '../components/Logo.svelte';
import PageHeader from '../components/PageHeader.svelte';
</script>
    
<div class="contentSimulator">
    <PageHeader><h1>På Phoenix LAN</h1></PageHeader>
    <div class="content">
        <div class="content-inner">
            <h1>Hva er tilgjengelig?</h1>
            <p>På arrangemanget er det en cafè, denne opereres av Radar.
                Den er åpen under hele phoenix, så selv om butikkene er stengt vil det fremdeles være mulig å kjøpe mat og drikke.</p>
            <p>Under arrangementet vil det være en sovesal tilgjengelig for deltagere og crew, fredag kveld til søndag morgen.
                Det er <b>ikke tillatt å sove på plassen</b>, crewet vil henvise sovende deltagere til sovesalen.
                Det er ikke tilatt å oppbevare eiendeler i sovesalen når de ikke blir brukt.</p>
            <p>Det vil være datahjelp/tech support under hele arrangementet. Dette gjelder kun arrangement-relevante problemer. Vi har ikke mulighet til å gjøre fysiske endringer på maskinen din, for å hindre at phoenix eller crewet skal stå annsvarlig for eventuelle feil eller skader som kan forekomme.
                Tech support / datahjelp vil ikke kunne hjelpe med rekvisita som saks og gaffateip.
                Det er en vannstasjon både på Radar Cafè og i Tech-desken.</p>
            <h1>Informasjon om plassen</h1>
            <p>Hver plass er minimum <b>70x70cm</b>.
                Det er lov til å ta med hylle, men den kan ikke gå utenom plassen.
                Du kan også ta med egen stol, men da bare en vanlig kontorstol. Ikke noe stor stressless, tenk på sidemannen</p>
            <p>Det vil være mulighet for tilkobling av bare ett strømuttak per deltager.
                Ta derfor med strømforgrener etter behov.
                Det er ikke lov å ta med hvitevarer.</p>
            <p>	Det settes opp switcher på bordene, der du kan sette inn din egen kabel. Vi anbefaler en kabel på minimum 10 meter.
                Det er lagt opp til 1 port per person.
                Det er ikke tillatt å ta eget nettverksutstyr. Unntaket er "dumme" svitsjer som ikke skaper problemer.
                Det er ikke tillatt å koble ut andre kabler fra switchen.</p>
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