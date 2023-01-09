<script>
    import { Link } from "svelte-routing";
    import Logo from '../components/Logo.svelte'
import PageHeader from "../components/PageHeader.svelte";
</script>

<div class="contentSimulator">
    <PageHeader><h1>Konkurranser</h1></PageHeader>
    <div class="content">
        <div class="content-inner">
            <p>Flere konkurranser vil bli lansert senere</p>
            <h2>Valorant 3v3</h2>
            <p><i>Mer informasjon kommer senere</i></p>
            <p><i>Vi erstatter dette LANet CS:GO med valorant</i></p>
            <h2>Minecraft Battle Royale</h2>
            <p><i>Mer informasjon kommer senere</i></p>
            <h2>Phoenix Datasnok</h2>
            <p>Er <b>DU</b> god på data? Vis dine ferdigheter ved å delta på Datasnok, en "hacke-rebus" du vinner ved å løse oppgaver av forskjellig vanskelighetsgrad.</p>
            <p><i>Mer informasjon kommer senere</i></p>
			<h2>Minecraft Build Battle</h2>
            <p><i>Mer informasjon kommer senere</i></p>
            <h2>Beatsaber:</h2>
            <p><i>Mer informasjon kommer senere</i></p>
            <h2>Mange småkonkurranser</h2>
            <p>I løpet av LANet vil det arrangeres tilfeldige småkonkurranser du kan delta på for å få et avbrekk fra dine vanlige spill. Noen vil være fysiske, andre vil være digitale.</p>
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
