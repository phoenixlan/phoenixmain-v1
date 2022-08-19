<script>
	import Fa from 'svelte-fa'
	import { Router, Link, Route } from "svelte-routing";
	import Main from './pages/Main.svelte'
	import Packing from './pages/Packing.svelte'
	import Rules from './pages/Rules.svelte'
	import Agenda from './pages/Agenda.svelte'
	import NotFound from './pages/NotFound.svelte'
	import Parents from './pages/Parents.svelte'
	import AtTheEvent from './pages/AtTheEvent.svelte'
	import Competitions from './pages/Competitions.svelte'
	import PurchaseTos from './pages/PurchaseTos.svelte'

	import { faChild } from '@fortawesome/free-solid-svg-icons'
	import { faShieldAlt } from '@fortawesome/free-solid-svg-icons'
	import { faList } from '@fortawesome/free-solid-svg-icons'
	import { faTrophy } from '@fortawesome/free-solid-svg-icons'
	import { faCalendarAlt } from '@fortawesome/free-solid-svg-icons'

	import { faInstagram } from '@fortawesome/free-brands-svg-icons'
	import { faFacebook } from '@fortawesome/free-brands-svg-icons'

	export let url = "";

	// https://github.com/EmilTholin/svelte-routing/issues/132
	history.pushState = new Proxy(history.pushState, {
		apply (target, thisArg, argumentsList) {
			// scrollTo(0, 0) <-- order of operation can mather (ty, @t-lock)
			Reflect.apply(target, thisArg, argumentsList)
			scrollTo(0, 0)
		}
	})

</script>

<Router url="{url}">
	<main>
		<Route path="pakkeliste" component="{Packing}" />
		<Route path="regler" component="{Rules}" />
		<Route path="salgsbetingelser" component={PurchaseTos} />
		<Route path="agenda" component="{Agenda}" />
		<Route path="foreldre" component="{Parents}" />
		<Route path="pa_phoenix" component="{AtTheEvent}" />
		<Route path="konkurranser" component="{Competitions}" />
		<Route path="/"><Main /></Route>
		<Route path="" component="{NotFound}" />
	</main>

	<footer class="samarbeidspartnere">
		<h2>Phoenix LAN på sosiale medier</h2>
		<div class="some-list">
			<a href="https://www.instagram.com/phoenixlan.no/">
					<Fa icon={faInstagram} />
			</a>
			<a href="https://www.facebook.com/phoenixlan.no">
					<Fa icon={faFacebook} />
			</a>

		</div>
		<h2>Samarbeidspartnere</h2>
		<div class="sponsors">
			<a href="https://asker.kommune.no">
				<img class="sponsor" src="images/sponsors/asker_kommune.svg" alt="Asker Kommune" />
			</a>
			<a href="https://www.homenet.no/">
				<img class="sponsor" src="images/sponsors/homenet.png" alt="Homenet | Full fart & full frihet" />
			</a>
			<a href="https://viken.no/bleiker-vgs/">
				<img class="sponsor" src="images/sponsors/bleiker.png" alt="Bleiker VGS" />
			</a>
		</div>
		<h2>Kontakt</h2>
		<div class="credits">
			<p>info@phoenixlan.no</p>
		</div>
		<div class="hack" />

	</footer>
</Router>
<style>
	main {
		/* height: 100%; */
		text-align: center;
		max-width: none;
		margin: 0 auto;
		min-height: 100%;
		color: white;
		background-color: #111;
	}

	footer {
		/* height: 100%; */
		text-align: center;
		max-width: none;
		margin: 0 auto;
		color: white;
	}

	/* Refactor to child page at some point */
	.contentSimulator {

	}

	.some-list {
		font-size: 2.5em;
		height: 2em;
	}

	.some-list > a{
		color: white;
		margin: 0.2em;
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
	}

	/* END refactor to child page at some point */

	.sponsors {
		margin: 1em;
	}

	footer {
		padding-top: 1rem;
		background-color: #111111;
	}

	.sponsor {
		max-height: 3em;
		height: 3em;
		max-width: 90%;
		margin: 0.2em;
	}

	.hack {
		height: 5em;
	}
</style>