<!--
__________.__                         .__        
\______   \  |__   ____   ____   ____ |__|__  ___
 |     ___/  |  \ /  _ \_/ __ \ /    \|  \  \/  /
 |    |   |   Y  (  <_> )  ___/|   |  \  |>    < 
 |____|   |___|  /\____/ \___  >___|  /__/__/\_ \
               \/            \/     \/         \/
Liker du programmering og teknologi? Søk Tech, da vel!
-->
<script>
    import Fa from 'svelte-fa'

	import { faSnowflake } from '@fortawesome/free-solid-svg-icons'
	import { faLeaf } from '@fortawesome/free-solid-svg-icons'
	import { faComputer } from '@fortawesome/free-solid-svg-icons'
	import { faGamepad } from '@fortawesome/free-solid-svg-icons'
	import { faAward } from '@fortawesome/free-solid-svg-icons'
	import { faVrCardboard } from '@fortawesome/free-solid-svg-icons'
	import { faUserPlus } from '@fortawesome/free-solid-svg-icons'
	import { faMicrochip } from '@fortawesome/free-solid-svg-icons'
	import Background from '../components/Background.svelte';

	import Logo from '../components/Logo.svelte';

	const API_URL = __myapp.env.API_URL
	const APP_HOST = __myapp.env.APP_HOST
	const APP_PROTOCOL = __myapp.env.APP_PROTOCOL
	console.log(__myapp.env)

	const fetchMetadata = (async () => {
		const response = await fetch(`${API_URL}/event/current`)
		const current_event = await response.json()

		const [ ticket_types, ticket_availability ] = await Promise.all([
			await (await fetch(`${API_URL}/event/${current_event.uuid}/ticketType`)).json(),
			await (await fetch(`${API_URL}/event/${current_event.uuid}/ticket_availability`)).json(),
		])
		

		console.log(ticket_types)
		return {
			event: current_event,
			ticket_types,
			ticket_availability
		}
	})()

	const getMinTicketPrice = (ticket_types) => {
		let lowest = Number.MAX_SAFE_INTEGER
		ticket_types.forEach((type) => {
			if(!type.seatable) {
				return
			}
			if(type.price < lowest) {
				lowest = type.price
			}
		})
		return lowest
	}
	const getMaxTicketPrice = (ticket_types) => {
		let highest = 0
		ticket_types.forEach((type) => {
			if(type.price > highest) {
				highest = type.price
			}
		})
		return highest
	}
	const localeFormatSettings = {
        month: 'long',
        day: 'numeric',
        hour: '2-digit',
        minute: '2-digit',
		timeZone: "Europe/Oslo"
    }
</script>

<main>
	<div class="splash-background-sandwitch">
		<Background />
		<div class="splash">
			<div class="splash-inner">
				<Logo />
				<h2 class="lanTitle">Gaming og Digital kultur i Asker Kulturhus</h2>
				{#await fetchMetadata}
				{:then data}
				<div class="button_container ticket_button_container">
					<a href={`${APP_PROTOCOL}://delta.${APP_HOST}`}>
						<div class="buy_ticket_btn">
							<h2>Delta</h2>
						</div>
					</a>
				</div>
				<div class="ticketDetail">
					<h3>{new Date(data.event.start_time*1000).toLocaleString('no-NO', localeFormatSettings)} til {new Date(data.event.end_time*1000).toLocaleString('no-NO', localeFormatSettings)}{(data.event.location?.name) ? (" I " + data.event.location.name) : ""}</h3>
					{#if data.event.booking_time < new Date().getTime()/1000}
					<h3>
						{data.ticket_availability.total} billetter igjen.
						{#if data.ticket_types.length > 0}
							Fra {getMinTicketPrice(data.ticket_types)},-
						{/if}
					</h3>
					{:else}
					<h3>
						Billetter slippes {new Date(data.event.booking_time*1000).toLocaleString('no-NO', localeFormatSettings)}.
						{#if data.ticket_types.filter(ticket_type => ticket_type.seatable).length > 0}
							Fra {getMinTicketPrice(data.ticket_types)},-
						{/if}
					</h3>
					{/if}
				</div>
				{:catch error}
				<b>Kunne ikke hente data</b>
				{/await}
			</div>
		</div>
	</div>
	<div class="explanation">
		<h2>Om arrangementet</h2>
		<div class="editions">
			<div class="edition">
				<Fa class="edition-icon" icon={faSnowflake} />
				<s>
				<h3>Vinterferie</h3>
				<p>1 natt(Lørdag til Søndag)<br />Første helgen</p>
				<p>Aldersgrense til og med 20 år<br /><i>(25 for crew)</i></p>
				</s>
				<p><b>NB: Ingen vinter-LAN i 2024 pga budsjettkutt i kommunen</b></p>
			</div>
			<div class="edition">
				<Fa class="edition-icon" icon={faLeaf} />
				<h3>Høstferie</h3>
				<p>2 netter(Fredag til Søndag)<br />Første helgen</p>
				<p>Aldersgrense til og med 25 år</p>
			</div>
		</div>

		<h2>Hva kan jeg gjøre på Phoenix LAN?</h2>
		<div class="editions">
			<div class="edition">
				<Fa class="edition-icon" icon={faVrCardboard} />
				<h3>Spille VR</h3>
				<p>Phoenix stiller med flere VR-stasjoner der du kan prøve VR-spill</p>
			</div>
			<div class="edition">
				<Fa class="edition-icon" icon={faComputer} />
				<h3>Spille på medbragt PC/konsoll</h3>
				<p>Hver deltaker får en sitteplass med internett(gigabit ethernet) og strøm. WiFi er ikke garantert, da det ikke er egnet for gaming</p>
			</div>
			<div class="edition">
				<Fa class="edition-icon" icon={faGamepad} />
				<h3>Spille på arkademaskiner</h3>
				<p>Vi stiller med flere fysiske arkademaskiner, både retro og moderne</p>
			</div>
			<div class="edition">
				<Fa class="edition-icon" icon={faAward} />
				<h3>Konkurrere om premier</h3>
				<p>Vi har en premiepott på over 10k. Hvor mye av den klarer du å vinne?</p>
			</div>
			<div class="edition">
				<Fa class="edition-icon" icon={faUserPlus} />
				<h3>Møte nye lagkamerater</h3>
				<p>Phoenix LAN er en av de beste stedene å gå i vinterferien og høstferien for å møte likesinnede i Asker og Bærum.</p>
			</div>
			<div class="edition">
				<Fa class="edition-icon" icon={faMicrochip} />
				<h3>Lære om tech</h3>
				<p>Vi tilbyr mange måter å lære mer om teknologi med oss, blandt annet ved hjelp av vår egen CTF.</p>
			</div>
		</div>

		<p>Phoenix LAN er en møteplass for ungdom I Asker der de kan dele og dyrke sin interesse for digital kultur med andre. Det er først og fremst et LAN-party der vi også legger vekt på aktiviteter utenom datamaskinen du tok med. I tillegg til en sitteplass der du kan ta med en PC, vil vi ha aktiviteter som VR-stasjoner, konsoller, og arkademaskiner.</p>

		<h2>Bli med på å arrangere moroa</h2>

		<p>Phoenix LAN er et ungdomsarrangement der ungdom står for mye av den frivillige kraften bak arrangementet. Vi vil aldri kunne være noe uten de frivillige som står på for at lanet skal kunne gå rundt. På Phoenix finnes det mange grupper med forskjellige arbeidsoppgaver, fra vertskap og mat, konkurranser og underholdning, til drift av det tekniske.</p>

		<p>Vil du være med på å arrangere en plattform der likesinnede kan møtes for å delta i digital kultur trenger vi <b>DEG</b>!</p>

		<div class="button_container ticket_button_container">
			<a href="https://delta.phoenixlan.no/">
				<div class="buy_ticket_btn">
					<h2>Søk crew</h2>
				</div>
			</a>
		</div>

		<div class="button_container">
        </div>
		<h2>Sosialt</h2>
		<p>Imellom arangementene kan du henge på vår discord-server. Her kan du holde kontakt med de du møtte under LANet, og stille spørsmål. Phoenix-miljøet er moderert, men det samme kan ikke sies om andre steder på Discord. Vi anbefaler derfor foreldre å passe på hva barn under 18 gjør på Discord, og hvilke miljøer de er med i.
		<!-- I am sorry to my ancestors for this ugly button -->
		<div class="button_container ticket_button_container">
			<a href="https://discord.gg/sbwJ9wPw28">
				<div class="buy_ticket_btn">
					<h2>Bli med i discord</h2>
				</div>
			</a>
		</div>
		<h2>Spørsmål</h2>
		<p>Spørsmål kan sendes til info@phoenixlan.no</p>
	</div>
</main>

<style>
	.button_container > :global(a) {
        user-select: none;

        color: white;
		text-decoration: none;
	}

	.editions {
		display: flex;
		justify-content: center;
		flex-wrap: wrap;

		margin: 3em 0 3em 0;
	}

	.edition {
		margin: 0 2em 0 2em;
		width: 20em;
	}
	
	:global(.edition > svg) {
		font-size: 3em;
		margin: 1em;
		color: #f451a0;
	}


	@font-face {
		font-family: noContinue;
		src: url("/fonts/gomarice_no_continue.ttf");
	}

	.lanTitle {
		font-family: noContinue;
	}

	@keyframes fadeIn {
		0% { opacity: 0; }
		100% { opacity: 1; }
	}
	.ticketDetail {
		animation: fadeIn 0.2s;
	}
	.sponsors {
		margin: 1em;
	}

	.sponsor {
		max-height: 3em;
		height: 3em;
		max-width: 90%;
	}

	.explanation {
		padding: 1rem 2rem 1rem 2rem;
		background-color: #111111;
	}

	.splash-background-sandwitch {
		position: relative;
		min-height: calc(100vh - 10em);
	}

	.splash {
		width: 100%;
		height: 100%;
		display: flex;
		justify-content: center;
	}

	.splash-inner {
		z-index: 1;
		margin: 2em 2em 0 2em;
	}

	.hack {
		height: 5em;
	}

	.button_container {
		margin: 2em 0 2em 0;
		display: flex;
		flex-direction: row;
		flex-wrap: wrap;
		justify-content: space-around;
		
		width: 100%;
    }

	.button_container :global(a) {
		text-decoration: none;
	}
	.ticket_button_container :global(a) {
		width: 100%;
		max-width: 30em;
		margin: 1em 0 1em 0;
	}

	.join_discord_btn {
		color: white;
		background-color: #f451a0;

		cursor: pointer;
		display: flex;
		flex-direction: column;
		justify-content: center;
		width: 25em;
		height: 6em;
	}
	.join_discord_btn > h2 {
		text-decoration: none;

	}
	.join_discord_btn:hover {
		background-color: #C42180;
	}

	.buy_ticket_btn {
		color: white;
		background-color: #f451a0;

		cursor: pointer;
		display: flex;
		flex-direction: column;
		justify-content: center;

		max-width: 30em;
		width: 100%;
		height: 6em;
	}
	.buy_ticket_btn > h2 {
		text-decoration: none;

	}
	.buy_ticket_btn:hover {
		background-color: #C42180;
	}

	@media only screen and (min-width: 600px) {
		.article_link_container {
			width: 30em;
			height: 21em;
			margin: 2em;
		}
	}
	@media only screen and (max-width: 600px) {
		.button_container {
			flex-direction: column;
			align-items: center;
		}
		.button_container > :global(a) {
			width: 100%;
		}
	}

    /*.button_container > a {
        color: red;
        text-decoration: none;
    }*/

	.discord_button_container {
		width: 100%;
		display: flex;
		justify-content: center;
	}

	.discord_button {
		background-color: #f451a0;
		padding: 2em;
		width: 20em;
		cursor: pointer;
		display: flex;
		flex-direction: column;
		justify-content: space-around;
	}

	.article_link_container:hover {
		background-color: #C42180;
	}

	.article-icon {
		color: white;
		font-size: 7em;
	}

	h1 {
		color: #ffffff;
		text-transform: uppercase;
		font-size: 3em;
		font-weight: 100;
	}

	h2 {
		color: #ffffff;
		text-transform: uppercase;
		font-size: 2em;
		font-weight: 100;
		margin: 0;
	}
	
	h3 {
		color: #ffffff;
		text-transform: uppercase;
		font-size: 1.9em;
		font-weight: 100;
		margin: 0;
	}



	@media only screen and (min-width: 960px) {
		h1 {
			font-size: 4em;
		}
		h2 {
			font-size: 3em;
		}
	}

	p {
		color: #ffffff;
		max-width: 60em;
		margin: 1em auto 3em auto;
		line-height: 1.5em;
	}

	img {
		max-width: 80%;
	}

</style>
