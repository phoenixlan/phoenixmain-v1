<script>
    import Background from './Background.svelte'
    import Logo from '../components/Logo.svelte'
</script>

<div class="splash">
    <div class="splash-inner">
        <Logo />
        <slot></slot>
    </div>
    <Background />
</div>

<style>

.splash {
    min-height: 30vh;
    display: flex;
    justify-content: center;
    position: relative;
}

.splash-inner {
    margin-top: 2em;
    z-index: 1;
}

.splash-inner > img {
    width: 20em;
}
</style>