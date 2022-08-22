<script>
import PageHeader from '../components/PageHeader.svelte';
</script>
    
<div class="contentSimulator">
    <PageHeader><h1>Hva er et LAN?</h1></PageHeader>
    <div class="content">
        <div class="content-inner">

		<p>Et LAN-party er et arrangement der fokus er å samles under samme tak for å spille på datamaskinen. Dette var enda viktigere før i tiden, når plattformer som Discord ikke eksisterte, og online-spill var unntaket, ikke normen</p>

        <p>Spill pleide ikke å tillate å spille over nettet i stor grad, noe som ofte gjorde det nørvendig å samles slik at man kunne spille lokalt i stedet. Det var ikke uvanlig at spillutviklere ga ut serveren deres(et program som brukes for å "arrangere" et online-spill), noe som blant annet gjorde det lett å arrangere lokale turneringer.</p>

        <p>MMO spill har også vært populært, spesielt World of Warcraft. Selv om spillet har hatt en kompetitiv komponent, var det vanligste å delta i "guilds", en organisert gruppe mennesker som jobber sammen for å bekjempe sterke fiender. Disse guildene kunne ofte finne på å møtes på et LAN for å jobbe og sosialisere, ikke veldig forskjellig fra en helgtur med jobben.</p>

        <p>Før fiber spredde seg i Norge var det også populært å besøke LAN for å oppleve hvordan det var å surfe på nettet med rask tilkobling, da LAN ofte hadde vesentlig bedre linje enn det en kunne få hjemme.</p>

        <p>Data-samlingerhar historisk vært hjembanen til flere kreative subkulturer. <a href="https://en.wikipedia.org/wiki/Demoscene">Demoscenen</a> har stått sterkt i Norge. The Gathering, Norges største LAN party, var opprinnelig et "demoparty" der å spille dataspill ble sett ned på. "Demoscenere" møttes på demoparties for å sammenligne og konkurrere i kreative ferdigheter som grafikk og programmering, der målet ofte var å vise at de kunne få til ting som ble sett på som utfordrende med dagens datamaskiner.</p>

        <p>LAN-parties har også blitt sammenlignet med copyparties, et fenomen fra før internett der folk møttes for å dele programvare ved hjelp av disketter</p>
            
        <p>I dag er LAN-parties mindre nødvendig, men brukes enda som en møteplass for folk interessert i digital kultur. Formålet har gått fra å være en nødvendighet for spille med andre, til å være en plass før å møte internett-venner og likesinnede i næromerådet.</p>
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