<script>
    import Logo from '../components/Logo.svelte';
import PageHeader from '../components/PageHeader.svelte';
</script>
    
<div class="contentSimulator">
    <PageHeader><h1>For foreldre</h1></PageHeader>
    <div class="content">
        <div class="content-inner">
            <h1>Er barnet under 14?</h1>
            <p>Dersom barnet er under 14 må hen ta med en foreldreattest som leveres under innsjekking. Dette gjøres for å sørge for at foreldrene er kjent med lokasjonen til barnet sitt.</p>

            <!--<p>Foreldreattesten finner du her!</p> -->
            <p>En foreldreattest vil bli sluppet før neste fysiske LAN</p>
            <h1>Portforbud for barn under 15</h1>
            <p>Vi har innført portforbud imellom 23:00 og 7:00. Dette er gjort for å stoppe unge barn fra å gå rundt alene i Asker sentrum om natta. Dersom barnet skal få lov til å gå ut av bygget i portforbud-tiden må dere ta med foreldreattesten(selv om de er over 14).
            </p>

            <h1>Hvordan foregår det?</h1>
            <p>Arrangementet varer over tre dager – normalt fra fredag kveld til søndag morgen, første helgen i høstferien og vinterferien. 
                Infected er for ungdom – og utføres av ungdom. Det vil si at det er primært ungdommen selv som står for arrangementet, med planlegging, gjennomføring og opprydding. 
                På denne måten blir arrangementet en sosial arena der unge mennesker kan bygge opp relasjoner og drive positivt arbeid.</p>
            
            <h2>Oppmøte</h2>
            <p>Når LAN-et starter klokken 18 sjekker alle deltakerne inn, får på adgangsbånd og finner plassen sin.
                Her plasserer de pc-en og sitter store deler av tiden.
                Ellers er Radar Ungdomskafe åpen, og områdene i kafeen er åpent for sosiale aktiviteter.
                Det er egne sovesaler, og deltakerne blir oppfordret til å sove flere ganger underveis.
                Ellers foregår det spillkonkurranser lokalt, og andre «events» og konkurranser på scenen.</p>
                
            <h2>Sikkerhet</h2>
            <p>Det er over 100 medlemmer i Infected-crewet som hele tiden overvåker områdene i form av faste vaktposter og streifelag som går rundt omkring på bygget.
            Sikkerhet er en stor satsning for Infected, som er tydelig ved at det desidert største crewet er vertskapsorientert.
            Infected sørger også for sikkerhet i form av kriseberedskap og førstehjelp.
            Skulle du bli bekymret, ta kontakt med crew underveis.
            Vi har tett samarbeid både med Brannvesen og Politi, som derfor kan komme innom under arrangementet.</p>

            <h2>Kontakt</h2>
            <p>Vi oppfordrer alle til å ha med seg mobil på arrangementet.
            Skulle det komme situasjoner hvor du må må ha tak i vedkommende og ikke får kontakt, kan du kontakte crew.</p>

            <h1>Er det en aldersgrense på Phoenix LAN?</h1>
            <p>Det er ingen nedre aldersgrense, men barnet må ta med foreldreattest dersom hen er yngre enn 14. 
                Det er opp til deg som forelder å vite når barnet ditt er klar til å være alene(eller alene med venner) en helg. 
                Ofte ser vi et kompromiss der yngre barn enten må sove hjemme om nettene, eller drar med venner som er litt eldre.</p>
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