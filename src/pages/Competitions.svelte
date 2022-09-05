<script>
    import { Link } from "svelte-routing";
    import Logo from '../components/Logo.svelte'
import PageHeader from "../components/PageHeader.svelte";
</script>

<div class="contentSimulator">
    <PageHeader><h1>Konkurranser</h1></PageHeader>
    <div class="content">
        <div class="content-inner">
            <h2>CS:GO Wingman 2v2</h2>
            <p>Mer informasjon kommer</p>
            <h2>Minecraft Battle Royale</h2>
            <p>Alle vs alle, Hunger Games style. Bare den beste vil stå igjen til slutt</p>
            <h2>Minecraft Build Battle</h2>
            <p>En jury kårer beste build. Konkurransen starter når dørene åpner</p>
            <h2>Phoenix Datasnok</h2>
            <p>Er <b>DU</b> god på data? Vis dine ferdigheter ved å delta på Datasnok, en "hacke-rebus" du vinner ved å løse oppgaver av forskjellig vanskelighetsgrad.</p>
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
</style>