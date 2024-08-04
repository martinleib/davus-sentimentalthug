<script>
    import Countdown from "./Countdown.svelte";
    import Links from "./Links.svelte";

    let tracklist = [
        { id: 1, artists: "Davus", title: "CAE LA NOCHE", feat: "LESTON"},
        { id: 2, artists: "Davus", title: "NO HABLES MÁS", feat: "LESTON"},
        { id: 3, artists: "Davus", title: "TODO POR NOSOTROS", feat: "WAVE"},
        { id: 4, artists: "Davus", title: "NO PUEDO CREER" },
        { id: 5, artists: "Davus", title: "CARTA A TU NOVIA" },
        { id: 6, artists: "Davus", title: "BLANCO" },
        { id: 7, artists: "Davus", title: "UN PAR DE SECUENCIAS" },
        { id: 8, artists: "Davus", title: "ASTUCIA", feat: "ZOE"},
        { id: 9, artists: "Davus", title: "CREO QUE NO" }
    ];

    import cover from "../assets/cover.jpeg";
</script>

<main class="text-center mt-4 container">
    <figure class="figure pt-4 mb-0 pb-4">
        <img
            src={cover}
            alt="Cover art de Sentimental Thug"
            class="figure-img img-fluid coverart"
            draggable="false"
        />
    </figure>

    <time class="countdown-wrapper pt-3 pb-3">
        <Countdown />
    </time>
    
    <section class="pt-4 px-2">
        {#each tracklist as track}
            <div class="tracklist">
                <div class="svelte-track-group mb-3">
                    <h5 class="trackname fs-6 mb-0 text-uppercase">
                        0{track.id}.
                        <span class="davus-accent-color">{track.artists}</span> - {track.title}
                    </h5>
                    {#if track.feat}
                        <p class="fs-6 m-0"><em>ft. <span class="davus-accent-color">{track.feat}</span></em></p>
                    {/if}
                </div>
            </div>
        {/each}
    </section>

    <section class="links-wrapper pt-4 pb-4">
        <Links />
    </section>
</main>

<style>
    .coverart {
        width: 300px;
        position: relative;
        z-index: 1;
    }
</style>
