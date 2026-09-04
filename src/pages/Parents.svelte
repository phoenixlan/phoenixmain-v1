<script>
    import Logo from '../components/Logo.svelte';
    import PageHeader from '../components/PageHeader.svelte';

	const APP_HOST = __myapp.env.APP_HOST
	const APP_PROTOCOL = __myapp.env.APP_PROTOCOL
</script>

<div class="contentSimulator">
    <PageHeader><h1>For foreldre</h1></PageHeader>

    <div class="content">
        <div class="content-inner">
            <div class="parents-body">
                <div class="parents-container">
                    <div class="parents-information">
                        <h2>Om Phoenix LAN</h2>
                        <p>Phoenix LAN er et LAN party / datatreff arrangert av ungdommer, for ungdommer for spill, og tech interesserte i Asker og omegn.</p>
                        <p>Arrangementet er under ungdomsorganisasjonen Radar Event, med et tett samarbeid med ungdomsavdelingen UngKultur Asker som er ansvarlig for drift av ungdomsklubbene i hele Asker kommune, og kulturarrangementer som UKM, Asker festivalen, og Nattkino.</p>
                    </div>

                    <div class="parents-information">
                        <h2>Våres mål og ambisjoner</h2>
                        <p>Vi har to mål. Å skape en møteplass for spill- og tech interesserte ungdommer, og tilby muligheten til å prøve ting man kanskje ikke har hjemme.</p>
                        <p>Vi arrangerer LAN party første helgen i høstferien hvor vi åpner dørene fredag kveld, og avslutter søndag morgen. Vi ønsker å skape en innholdsrik helg for alle som kommer hvor man kan henge med venner, spille, delta på konkurranser, overnatte, og bruke tiden på et stort arkaderom som er fylt med utstyr man kanskje ikke har hjemme. Dette er alt fra VR stasjoner, til racing simulatorer, Nintendo switch med et stort utvalg spill, og arkademaskiner.</p>
                        <p>Det mest positive med ungdoms-LAN er mulighet for å bli kjent med, og være sosial med ungdom med like interesser. Vi tror mange ungdommer har stor glede av gaming i en mer sosial setting. Se på det som et sosialt og morsomt <i>tre-dagers all you can game</i> arrangement for barn og unge!</p>
                    </div>

                    <div class="parents-information">
                        <h2>Av ungdom, for ungdom</h2>
                        <p>Arrangementet er drevet av frivillige ungdommer med støtte fra UngKultur Asker.</p>
                        <p>Det vil si at det er i stor grad ungdommen selv som står for arrangementet, med planlegging, gjennomføring og opprydding. På denne måten blir arrangementet en sosial arena der unge mennesker kan bygge opp relasjoner og drive positivt arbeid. Vi oppfordrer ungdom til å melde seg inn i crew, og bidra til å utvikle og gjennomføre dette arrangementet.</p>
                        <p>UngKultur Asker stiller med ungdomsarbeidere som bidrar med å sikre, og hjelpe til under arrangementet. På dagtid er det flere ansatte på jobb, på kvelds- og nattid er det mindre. UngKultur stiller med minimum 2 på jobb til enhver tid gjennom arrangementet i tillegg til de ansatte på driftsavdelingen til Asker kulturhus som vaktmester, og teknikere.</p>
                    </div>

                    <div class="parents-information">
                        <h2>Alder</h2>
                        <p>Som deltaker hos Phoenix LAN har vi en <b>anbefalt</b> nedre aldersgrense, og en øvre aldersgrense.</p>
                        <p>
                            Vår <b>anbefalte</b> nedre aldersgrense for å delta på Phoenix LAN er årskullet som starter i 8. klasse på ungdomsskolen, altså 13-års alderen. Vi understreker at dette ikke er en fast aldersgrense men en anbefaling.<br/>
                            Det vil si at barn under denne alderen kan delta, men at det er deg som forelder som er ansvarlig for å bestemme når barnet deres er moden nok til å dra.
                        </p>
                        <p>Vi oppfordrer barn under 13-års alderen til å gjøre avtale hjemme om sovetider, eventuelt henting for å sove hjemme, og avtaler om spill, inntak av godteri og lignende.</p>
                        <p>Vi har en øvre aldersgrense som er på 26 år. Etter fylte 26 år kan du ikke lenger delta på våres arrangement.</p>
                        <p>Som crew hos Phoenix LAN må du være mellom 13 og 26 år.</p>
                        <p>Ved kjøp av billett for yngre barn vil det være krav til kontaktinformasjon til foresatte.</p>
                    </div>

                    <div class="parents-information">
                        <h2>Portforbud for ungdom under 18</h2>
                        <p>Vi har innført portforbud imellom 23:00 og 06:00. Dette er gjort for å stoppe ungdom fra å gå rundt alene i Asker sentrum om natta.</p>
                        <p>Dersom barnet skal få lov til å gå ut av bygget i portforbud-tiden må vi ha kommunikasjon med foresatte. Dette gjelder også for ungdom som er med i crewet.</p>
                    </div>

                    <div class="parents-information">
                        <h2>Oppmøte og hva man skal ta med seg</h2>
                        <p>Deltakerne møter opp til arrangementets start, sjekker inn med billetten man kjøpte, eller har fått på <a href={`${APP_PROTOCOL}://delta.${APP_HOST}`}>billettsiden</a>, og får tildelt et adgangsbånd. Deretter finner man sitteplassen sin hvor man setter opp <b>sin egen</b> datamaskin og/eller konsoll, skjerm, tastatur, mus, og eventuelt medbragt stol. Vi stiller altså ikke med gaming-utstyr, dette skal man ta med selv.</p>
                        <p>Gjennom helgen så kan tiden brukes på sitteplassen sin for å spille med venner, og delta på konkurranser. Hvis man har lyst til på litt mer variasjon kan man gå til arkaderommet i multisalen for å prøve ting man ikke har hjemme. Tidligere har dette vært vr stasjoner, racing simulatorer, nintendo switch, m.m. Dersom man har lyst på mat, drikke eller snacks kan man bevege seg til Radar Kafé hvor det er servering. Når man til slutt er trøtt og har behov for å sove kan man gå til sovesalen i teatersalen for å sove.</p>
                    </div>

                    <div class="parents-information">
                        <h2>Sikkerhet</h2>
                        <p>Det er mange medlemmer i ungdoms-crewet, og ansatte fra UngKultur og kulturhuset, som hele tiden overvåker områdene i form av streifelag som går rundt omkring på bygget. Sikkerhet er en stor satsning for LANet. Det vil også være et innleid sanitets-vakt under hele arrangementet. Skulle du bli bekymret, eller lure på noe, ta kontakt med oss ansatte. Se kontaktinfo under.</p>
                        <p>Vi har også samarbeid både med Brannvesenet og Politiet som ofte kommer på besøk under arrangementet.</p>
                    </div>

                    <div class="parents-information">
                        <h2>Kontakt</h2>
                        <p>
                            <b>Avdelingsleder UngKultur</b><br/>
                            Nicolas Salvesen<br/>
                            <a href="tel:+4790566855">+47 905 66 855</a><br/>
                            <a href="mailto:nicolas.salvesen@asker.kommune.no">nicolas.salvesen@asker.kommune.no</a>
                        </p>
                        <p>
                            <b>Arrangementsansvarlig Ungkultur</b><br/>
                            Christian Nilsen<br/>
                            <a href="tel:+4748031628">+47 480 31 625</a><br/>
                            <a href="mailto:christian.nilsen@asker.kommune.no">christian.nilsen@asker.kommune.no</a>
                        </p>
                        <p>
                            <b>Vaktmestertelefon på kulturhuset (Døgnbemannet)</b><br/>
                            <a href="tel:+4766909634">+47 669 09 634</a>
                        </p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</div>

<style>

h2 {
    display: inline-block;
    margin-bottom: 0;
}
a {
    color: #f451a0;
    cursor: pointer;
}
a:hover {
    color: #fa83b6;
}

h2:after {
    content: " ";
    display: block;
    border: 2px solid #f451a0;
    width: 100%;
    margin-top: 0.4em;
}

.parents-body {
    display: flex;
    flex-flow: column;
    gap: 1em;
    max-width: 75em;
}

.parents-container {
    display: flex;
    gap: 1em;
    flex: 1;
    flex-flow: column;
}

.parents-information {
    margin: 0 1em;
}

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
  text-align: left;
  list-style-position: inside;
}
</style>