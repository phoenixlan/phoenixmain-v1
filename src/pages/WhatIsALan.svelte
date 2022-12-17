<script>
import PageHeader from '../components/PageHeader.svelte';
</script>
    
<div class="contentSimulator">
    <PageHeader><h1>Hva er et LAN?</h1></PageHeader>
    <div class="content">
        <div class="content-inner">

		<p>Et LAN-party er et arrangement der fokus er å samles under samme tak for å bruke teknologi på samme nettverk. Dette var enda viktigere før i tiden, når plattformer som Discord ikke eksisterte, og online-spill var unntaket, ikke normen. Navnet LAN kommer fra forkortelsen for Local Area Network, og ble brukt da en av de store poengene med å møte opp var å kunne dele et raskt lokalt nettverk, mye raskere enn hastigheten over internett hjemmefra. Før internett var utbredt blant husstander var LAN også den eneste måten en kunne spille med venner på tvers av flere datamaskiner.</p>

        <p>Spill pleide ikke å tillate å spille over internett i stor grad, noe som ofte gjorde det nødvendig å samles slik at man kunne spille lokalt i stedet. Det var ikke uvanlig at spillutviklere ga ut egen serverprogramvare til spillene deres, noe som blant annet gjorde det mulig å arrangere turneringer over lokalt nettverk. En spillserver er et program som både håndhever regler, holder styr på spillet, og fungerer som et knutepunkt som forteller alle spillere i spillet hva hverandre gjør. I dag er det få utviklere som gir ut denne programvaren. Den eneste måten å spille på er ofte på servere som kjøres offisielt av produsenten, eller ved å betale penger til et selskap som drifter en privat server på dine vegne. Dette gjøres av hensyn til kvalitet, men det har også gjort det mye vanskeligere for små miljøer å florere.</p>

        <p>MMO spill har også vært populært, spesielt World of Warcraft. Et MMO er et spill der du har en stor åpen verden der mange brukere er samlet og kan vandre fritt. Selv om spillet har hatt en kompetitiv komponent, var det vanligste å delta i "guilds", en organisert gruppe mennesker som jobber sammen for å bekjempe sterke fiender. Disse guildene kunne ofte finne på å møtes på et LAN for å jobbe og sosialisere, ikke veldig forskjellig fra en helgtur med jobben.</p>

        <p>Før fiber spredde seg i Norge var det også populært å besøke LAN for å oppleve hvordan det var å surfe på internett med rask tilkobling, da et LAN-party ofte hadde vesentlig bedre internetthastighet enn det en kunne få hjemme.</p>

        <p>Data-samlingerhar historisk vært hjembanen til flere kreative subkulturer. <a href="https://en.wikipedia.org/wiki/Demoscene">Demoscenen</a> har stått sterkt i Norge. The Gathering, Norges største LAN party, var opprinnelig et "demoparty" der å spille dataspill ble sett ned på. "Demoscenere" møttes på demoparties for å sammenligne og konkurrere i kreative ferdigheter som grafikk og programmering, der målet ofte var å vise at de kunne få til ting som ble sett på som utfordrende med dagens datamaskiner.</p>

        <p>LAN-parties har også blitt sammenlignet med copyparties, et fenomen fra før internett der folk møttes for å dele programvare ved hjelp av disketter, lenge før internett var raskt nok til å gjøre deling av filer praktisk. Her er det viktig å presisere at selv om piratkopiering definitivt fantest sted, var dette også en av de viktigste kildene til spredning av gratis programvare, såkalt "shareware". Phoenix LAN tillater ikke piratkopiering på sine arrangementer.</p>
            
        <p>I dag er LAN-parties mindre nødvendig, men brukes enda som en møteplass for folk interessert i digital kultur. Formålet har gått fra å være en nødvendighet for spille med andre, til å være en plass før å møte internett-venner og likesinnede i nærområdet.</p>
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