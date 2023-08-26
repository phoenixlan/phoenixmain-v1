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
            <ul>
                <li>Standard with OT</li>
                <li>No draws</li>
                <li>Up to 13 wins and/or 26 rounds(30-45 min)</li>
            </ul>
            <h2>Minecraft Battle Royale</h2>
            <p>Alle mot alle, Hunger Games style. Tre runder vil kjøres totalt. Total poengsum fra de tre rundene vil bestemme vinner, så lurt å slenge seg med på alt!</p>
            <h2>Phoenix Datasnok</h2>
            <p><b>Påmelding skjer via konkurransesystemet på LANet</b></p>
            <p>Er <b>DU</b> god på data? Vis dine ferdigheter ved å delta på Datasnok, en "hacke-rebus" du vinner ved å løse oppgaver av forskjellig vanskelighetsgrad.</p>
            <p>Konkurransetypene varierer fra "Finn det hemmelige passordet" til "Finn QR-koder gjemt på bygget" til "Finn sikkerhetshull i svak kode"</p>
            <ul>
                <li>Ingen teaming</li>
                <li>Flest poeng vinner</li>
                <li>Førstemann som fikk poengsummen blir valgt dersom det blir likt</li>
            </ul>
			<h2>Minecraft Build Battle</h2>
            <p>Er du mer interessert i bygging enn deathmatch?  Bygg i det frie gjennom LANet, og få sjansen til å vinne premie! En jury fra Phoenix Crew vil gå gjennom alle innslagene og gi vurderinger. Konkurransen starter så snart vi åpner, og du kan bygge frem til søn. kl 11. </p>
            <h2>Beatsaber:</h2>
            <p>Høyeste score på et sett med forhåndsbestemte sanger vinner. Du har hele LANet til å prøve deg.</p>
            <h2>Småkonkurranser</h2>
            <p>I løpet av LANet arrangerer vi småkonkurranser i alt fra bordtennis til </p>
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
</style>
