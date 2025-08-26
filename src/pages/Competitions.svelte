<script>
    import PageHeader from "../components/PageHeader.svelte";

    let infoVisibilityStates = [false, false, false, false]

    function toggleInfoVisibility(index) {
        infoVisibilityStates[index] = !infoVisibilityStates[index];
    }
</script>

<div class="contentSimulator">
    <PageHeader><h1>Konkurranser</h1></PageHeader>
    <div class="content">
        <div class="content-inner">
            <div class="compo-body">
                <!--
                <div class="compo-container">
                    <div class="compo-header-information">
                        <div>
                            <h2>Konkurranser</h2>
                            <p>Det er fortsatt lenge igjen til neste LAN, og vi har ikke planlagt hvilke konkurranser vi skal ha enda.</p>
                            <p>Har du forslag eller ønsker til hvilke konkurranser vi skal sette opp, kontakt oss på <a href="https://discord.gg/rSGtYEMQqh">Discord</a>!</p>
                            <p>Har du lyst til å være med og arrangere konkurransene anbefaler vi at du blir med i crewet, det gjør du ved å sende inn en crewsøknad <a href="https://delta.phoenixlan.no/crew">her</a>!</p>
                        </div>
                    </div>
                </div>
                -->
                <div class="compo-container">
                    <div class="compo-header-information">
                        <div>
                            <h2>Konkurranser (8)</h2>
                            <p>Her er listen for konkurransene med informasjon og påmeldingsskjema for årets LAN!<br/>Alle konkurransene arrangeres av tech/game crewet vårt.<br/>Er du interessert i å være med å arrangere konkurranser så kan du søke deg inn <a href="https://delta.phoenixlan.no/crew">her</a></p>    
                        </div>
                        <div>
                            <h2>Premiepott</h2>
                            <p>Premiepotten for årets LAN er på hele 12.000 kr, og spredt på vinnerne av de forskjellige konkurransene</p>    
                        </div>
                        <div>
                            <h2>Krav om påmelding</h2>
                            <p>VIKTIG! Vi krever at du melder deg på på forhånd for at vi skal kunne vite hvem som deltar, planlegge hvem som skal spille når til hvilke tider, og vite hvem vi skal kontakte dersom man vinner konkurransen. Samle laget ditt og bestem dere allerede nå hva dere vil delta på!</p>    
                        </div>
                    </div>
                </div>
                <div class="compo-container">
                    <div class="compo-card">
                        <div class="inner-card-container">
                            <div class="compo-container-body">
                                <div class="compo-body-title">
                                    <h3 class="compo-card-title">Fortnite</h3>
                                    <h4 class="compo-card-subtitle">Online, competitive, solo</h4>
                                </div>
                                <div class="compo-body-buttons">
                                    <a class="compo-button secondary" on:click={() => toggleInfoVisibility(0)}>Mer informasjon</a>
                                </div>
                                <div class="compo-body-information" style="height:{infoVisibilityStates[0] ? "100%" : "0px"}; overflow:hidden;">
                                    Informasjon:
                                    <li>Standard battle royale mode</li>
                                    <li>Opptil 6 runder (20-30 minutter, konkurransen kan ta opptil 3 timer)</li>
                                </div>
                            </div>
                        </div>
                    </div>

                    <div class="compo-card">
                        <div class="inner-card-container">
                            <div class="compo-container-body">
                                <div class="compo-body-title">
                                    <h3 class="compo-card-title">Minecraft • Battle Royale</h3>
                                    <h4 class="compo-card-subtitle">Online, competitive, solo</h4>
                                </div>
                                <div class="compo-body-buttons">
                                    <a class="compo-button secondary" on:click={() => toggleInfoVisibility(1)}>Mer informasjon</a>
                                </div>
                                <div class="compo-body-information" style="height:{infoVisibilityStates[1] ? "100%" : "0px"}; overflow:hidden;">
                                    Informasjon:
                                    <li>Alle mot alle, Hunger Games style</li>
                                    <li>Det blir arrangert 3 runder gjennom LANet</li>
                                    <li>Både kills og round wins gir poeng, de som vinner runden er ikke nødvendigvis de som vinner konkurransen!</li>
                                    <li>Den totale poengsummen fra alle tre rundene bestemmer hvem som vinner, så bli med på alle!</li>
                                    <li>Delta på mc.phoenixlan.no</li>
                                </div>
                            </div>
                        </div>
                    </div>

                    <div class="compo-card">
                        <div class="inner-card-container">
                            <div class="compo-container-body">
                                <div class="compo-body-title">
                                    <h3 class="compo-card-title">Minecraft • Build Battle</h3>
                                    <h4 class="compo-card-subtitle">Online, casual, solo</h4>
                                </div>
                                <div class="compo-body-buttons">
                                    <a class="compo-button secondary" on:click={() => toggleInfoVisibility(2)}>Mer informasjon</a>
                                </div>
                                <div class="compo-body-information" style="height:{infoVisibilityStates[2] ? "100%" : "0px"}; overflow:hidden;">
                                    Informasjon:
                                    <li>Byggekonkurranse basert på tema, blir publisert i serveren</li>
                                    <li>Alle byggverk blir gjennomgått og vurdert av en jury i crewet, beste byggverk vinner</li>
                                    <li>Vurderingskriterier er kreativitet, dybde i byggverk, variasjon, følge tema.</li>
                                    <li>Delta på mc.phoenixlan.no</li>
                                </div>
                            </div>
                        </div>
                    </div>

                    <div class="compo-card">
                        <div class="inner-card-container">
                            <div class="compo-container-body">
                                <div class="compo-body-title">
                                    <h3 class="compo-card-title">Datasnok</h3>
                                    <h4 class="compo-card-subtitle">Online, casual, solo</h4>
                                </div>
                                <div class="compo-body-buttons">
                                    <span class="compo-button secondary">Påmelding skjer på LANet gjennom eget system</span>
                                </div>
                                <div class="compo-body-information">
                                    <span>Er DU god på data? Vis ferdighetene dine ved å delta på Datasnok, en "hacke-rebus" hvor du vinner ved å løse oppgaver i forskjellige vanskelighetsgrader.</span><br/>
                                    <span>Konkurransetypene varierer fra "Finn det hemmelige passordet" til "Finn QR-koder gjemt på bygget" til "Finn sikkerhetshull i svak kode".</span><br/>

                                    <li>Ingen teaming</li>
                                    <li>Høyeste score vinner, eller førstemann som nådde samme score om det blir uavgjort</li>
                                </div>
                            </div>
                        </div>
                    </div>

                    <div class="compo-card">
                        <div class="inner-card-container">
                            <div class="compo-container-body">
                                <div class="compo-body-title">
                                    <h3 class="compo-card-title">Super smash</h3>
                                    <h4 class="compo-card-subtitle">Fysisk, casual, solo</h4>
                                </div>
                                <div class="compo-body-buttons">
                                    <span class="compo-button secondary">Påmelding skjer på LANet gjennom eget system</span>
                                </div>
                            </div>
                        </div>
                    </div>

                    <div class="compo-card">
                        <div class="inner-card-container">
                            <div class="compo-container-body">
                                <div class="compo-body-title">
                                    <h3 class="compo-card-title">Paint tegnekonkurranse</h3>
                                    <h4 class="compo-card-subtitle">Local, casual, solo</h4>
                                </div>
                                <div class="compo-body-information">
                                    <li>Delta på konkurransen ved å laste opp bildet i påmeldingsskjemaet over</li>
                                    <li>Alle tegninger blir gjennomgått og vurdert av en jury i crewet, beste tegningen vinner</li>
                                </div>
                                <div class="compo-body-information">
                                    <b>Regler for tegningen:</b>
                                    <li>Tegningen må lages i <b>Microsoft Paint</b></li>
                                    <li>Tegningen må lastes opp i .png format, dette er standard når du lagrer noe i Paint</li>
                                    <li>Innslaget kan ikke være en 1:1 kopi av et eksisterende verk</li>
                                    <li>Tegnebrett/tegneskjerm er tillatt</li>
                                </div>
                            </div>
                        </div>
                    </div>

                    <div class="compo-card">
                        <div class="inner-card-container">
                            <div class="compo-container-body">
                                <div class="compo-body-title">
                                    <h3 class="compo-card-title">Løpende konkurranser</h3>
                                    <h4 class="compo-card-subtitle">Fysisk, casual</h4>
                                </div>
                                <div class="compo-body-information">
                                    Gjennom LANet kommer vi til å arrangere småkonkurranser i multisalen<br/>
                                    <li>Beatsaber - Høyeste highscore gjennom helgen vinner</li>
                                    <li>Simulator racing, timetrial - Beste tiden vinner</li>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>  
            </div>
        </div>
    </div>
</div>
<style>
p {
    max-width: 60em;
}

h2 {
    display: inline-block;
    margin-bottom: 0;
}
a {
    color: #f451a0;
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
.content {
    padding: 1rem;
    background-color: #111111;
    display: flex;
    justify-content: center;
}
.content-inner{
  text-align: left;
  list-style-position: inside;
}


.compo-body {
    display: flex;
    flex-flow: column;
    gap: 1em;
}
.compo-header-information {
    margin: 0 1em;
}
.compo-container {
    display: flex;
    gap: 1em;
    flex: 1;
    flex-flow: column;
}
.compo-card {
    display: flex;
    flex: 1;
    border: 1px solid #f451a0;
    border-left: 1em solid #f451a0;
    padding: 1em 1.5em;
    margin: 0 1em;
}
.inner-card-container {
    display: flex;
    flex-flow: column;
    flex: 1;
}
.compo-container-body {
    display: flex;
    flex-flow: column;
    flex: 1;
    gap: 1.5em;
}
.compo-body-title {
    display: flex;
    flex-flow: column;
}
.compo-body-information {
    display: flex;
    flex-flow: column;
    font-size: 1em;
}
.compo-body-buttons {
    display: flex;
    flex-flow: row;
    gap: 1.5em;
}
.compo-button {
    display: flex;
    padding: .75em 1.5em;
    text-decoration: none;
}

.compo-card-title {
    font-size: 1.3em;
    margin: .15em 0;
    font-weight: 400;
}
.compo-card-subtitle {
    font-size: .8em;
    margin: .15em 0;
    font-weight: 100;
}

.primary {
    cursor: pointer;
    background-color: #f451a0;
    color: white;
}
.secondary {
    cursor: pointer;
    background-color: #b56eff;
    color: white;
}

@media screen and (max-width: 780px) {
    .compo-container {
        gap: 1.5em;
        width: 100vw;
    }
    .compo-card {
        border: 1px solid #f451a0;
        border-left: .5em solid #f451a0;
        padding: 1em 1.5em;
        margin: 0 1em;
    }
    .compo-body-buttons {
        flex-flow: column;
        gap: .5em;
    }
}
</style>
