<script>
    import { Link } from "svelte-routing";

    import Fa from 'svelte-fa'

	import { faHome } from '@fortawesome/free-solid-svg-icons'
	import { faChild } from '@fortawesome/free-solid-svg-icons'
	import { faShieldAlt } from '@fortawesome/free-solid-svg-icons'
	import { faList } from '@fortawesome/free-solid-svg-icons'
	import { faTrophy } from '@fortawesome/free-solid-svg-icons'
	import { faEthernet } from '@fortawesome/free-solid-svg-icons';
	import { faMapMarkerAlt } from '@fortawesome/free-solid-svg-icons'
	import { faCalendarAlt } from '@fortawesome/free-solid-svg-icons'

    export let open = true;
</script>
<aside class:hide={!open} on:click={() => open = false}>
    <Link to="/">
        <div class="article_link_container">
            <div class="article-icon">
                <Fa icon={faHome} />
            </div>
            <h3>Forside</h3>
        </div>
    </Link>
    <Link to="/foreldre">
        <div class="article_link_container">
            <div class="article-icon">
                <Fa icon={faChild} />
            </div>
            <h3>Forelder?</h3>
        </div>
    </Link>
    <Link to="/hvaErEtLan">
        <div class="article_link_container">
            <div class="article-icon">
                <Fa icon={faEthernet} />
            </div>
            <h3>Hva er et LAN?</h3>
        </div>
    </Link>
    <Link to="/regler">
        <div class="article_link_container">
            <div class="article-icon">
                <Fa icon={faShieldAlt} />
            </div>
            <h3>Regler og sikkerhet</h3>
        </div>
    </Link>
    <Link to="/konkurranser">
        <div class="article_link_container">
            <div class="article-icon">
                <Fa icon={faTrophy} />
            </div>
            <h3>Konkurranser</h3>
        </div>
    </Link>
    <Link to="/pakkeliste">
        <div class="article_link_container">
            <div class="article-icon">
                <Fa icon={faList} />
            </div>
            <h3>Pakkeliste</h3>
        </div>
    </Link>
    <Link to="/pa_phoenix">
        <div class="article_link_container">
            <div class="article-icon">
                <Fa icon={faMapMarkerAlt} />
            </div>
            <h3>På phoenix</h3>
        </div>
    </Link>
    <Link to="/agenda">
        <div class="article_link_container">
            <div class="article-icon">
                <Fa icon={faCalendarAlt} />
            </div>
            <h3>Tidsskjema</h3>
        </div>
    </Link>
</aside>
<style>
    .hide {
        display: none;

    }
    aside {
        color: white;
		background-color: #f451a0;

        z-index: 100;
        position: absolute;
    }

    @media only screen and (max-width: 600px) {
        aside {
            width: 100%;
        }
    }

	aside :global(a) {
        user-select: none;

        color: white;
		text-decoration: none;
	}

    .article-icon {
        width: 2em;
        padding: 0.5em;
    }

	.article_link_container {
        padding: 0em 1em 0em 0.5em;

		cursor: pointer;

		display: flex;
		flex-direction: row;
        justify-content: flex-start;
        align-items: center;
	}

    .article_link_container:hover {
		background-color: rgba(0, 0, 0, 0.1);
    }
</style>