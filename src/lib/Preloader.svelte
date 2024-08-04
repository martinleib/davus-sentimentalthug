<script>
    import { onMount } from 'svelte';
    export let duration = 3500;
    export let fadeDuration = 500;

    let showPreloader = true;
    let fadeOut = false;

    onMount(() => {
        document.body.classList.add('overflow-hidden');
        setTimeout(() => {
            fadeOut = true;
            setTimeout(() => {
                showPreloader = false;
                document.body.classList.remove('overflow-hidden');
            }, 500);
        }, 3500);
    });
</script>

{#if showPreloader}
    <div class="preloader {fadeOut ? 'fade-out' : ''}">
        <h1 class="preloader-text">SENTIMENTAL THUG</h1>
    </div>
{/if}

<style>
    .preloader {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background: #111;
        display: flex;
        justify-content: center;
        align-items: center;
        z-index: 1000;
        transition: opacity 0.5s ease;
    }

    .preloader-text {
        color: white;
        font-size: 2rem;
        text-transform: uppercase;
    }

    .fade-out {
        opacity: 0;
    }
</style>