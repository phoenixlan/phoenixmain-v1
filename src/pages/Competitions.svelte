<script>
    import { Link } from "svelte-routing";
    import Logo from '../components/Logo.svelte'
import PageHeader from "../components/PageHeader.svelte";
</script>

<div class="contentSimulator">
    <PageHeader><h1>Konkurranser</h1></PageHeader>
    <div class="content">
        <div class="content-inner">
            <h2>Konkurransene har ikke blitt sluppet enda...</h2>
            
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
    align-content: center;
    flex-direction: column;
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
</style>