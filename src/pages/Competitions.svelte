<script>
    import { Link } from "svelte-routing";
    import Logo from '../components/Logo.svelte'
import PageHeader from "../components/PageHeader.svelte";
</script>

<div class="contentSimulator">
    <PageHeader><h1>Konkurranser</h1></PageHeader>
    <div class="content">
        <div class="content-inner">
            <p>Er det konkurranser du savner? Si ifra til oss på Discord, eller søk Game crew og bli med på å arrangere det selv!</p>
            <h2>Valorant</h2>
            <p><a href="https://forms.gle/1UnhLSgG8KQu66Wt5">Påmelding(Lagledere)</a></p>
            <p><a href="https://forms.gle/krmoYmDxkvsSwvdt8">Påmelding(Lagmedlem)</a></p>
            <ul>
                <li>Standard with OT</li>
                <li>No draws</li>
                <li>Up to 13 wins and/or 26 rounds(30-45 min)</li>
            </ul>
            <h2>Minecraft Battle Royale</h2>
            <p><a href="https://forms.gle/JDjkPyEUYCfKR4bP6">Påmelding</a></p>
            <p>Alle mot alle, Hunger Games style. Tre runder vil kjøres totalt. Total poengsum fra de tre rundene vil bestemme vinner, så lurt å slenge seg med på alt!</p>
            <h2>Phoenix Datasnok</h2>
            <p><b>Påmelding skjer via konkurransesystemet på LANet</b></p>
            <p>Er <b>DU</b> god på data? Vis dine ferdigheter ved å delta på Datasnok, en "hacke-rebus" du vinner ved å løse oppgaver av forskjellig vanskelighetsgrad.</p>
            <ul>
                <li>Ingen teaming</li>
                <li>Flest poeng vinner</li>
                <li>Førstemann som fikk poengsummen blir valgt dersom det blir likt</li>
            </ul>
            <p><a href="https://datasnok.phoenixlan.no">datasnok.phoenixlan.no</a></p>
			<h2>Minecraft Build Battle</h2>
            <p><a href="https://forms.gle/MPNisMkfpZahe9379">Påmelding</a></p>
            <p>Er du mer interessert i bygging enn deathmatch?  Bygg i det frie gjennom LANet, og få sjansen til å vinne premie! En jury fra Phoenix Crew vil gå gjennom alle innslagene og gi vurderinger. Konkurransen starter så snart vi åpner, og du kan bygge frem til søn. Kl 11. </p>
            <h2>Beatsaber:</h2>
            <p>LAN’et har endelig VR! Den som greier høyeste high score i Beatsaber gjennom LANet får muligheten til å vinne premie. En bra mulighet til å teste spennende ny form for gaming uten å straffe lommeboka for alle som vil!</p>
            <h2>Småkonkurranser</h2>
            <h3>Paint</h3>
            <p><a href="https://forms.gle/utfwW9sPs1yiA22R7">Påmelding</a></p>
            <p>Ønsker du å tegne mellom matches? Lag et fint bilde gjennom LANet, og send til oss! En jury fra Phoenix Crew vil gå gjennom alle innslagene og gi vurderinger. Konkurransen starter så snart vi åpner, og du kan bygge frem til søn. Kl 11.</p>
        </div>
    </div>
</div>
<style>
p {
    max-width: 60em;
}
.content {
    padding: 1rem;
    background-color: #111111;
    display: flex;
    justify-content: center;
}
.center {
  text-align: center;
  list-style-position: inside;
}
</style>
