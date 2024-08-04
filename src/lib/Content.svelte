<script>
    import Countdown from "./Countdown.svelte";
    import Links from "./Links.svelte";

    const createRandomTitle = () => {
        const characters = "abcdefghijklmnopqrstuvwxyz0123456789";
        let result = "";

        for (let i = 0; i < 8; i++) {
            const randomInd = Math.floor(Math.random() * characters.length);
            result += characters[randomInd];
        }

        return `${result}`;
    };

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
    <div class="row m-auto">
        <div class="col-12">
            <figure class="figure pt-4 mb-0 pb-4">
                <img
                    src={cover}
                    alt="Cover art de Sentimental Thug"
                    class="figure-img img-fluid coverart"
                    draggable="false"
                />
            </figure>
        </div>
        <!-- <div class="col-6 col-md-4">
            <figure class="figure pt-4 mb-0 pb-4">
                <img
                    src={logo}
                    alt="Logo de Sentimental Thug"
                    class="figure-img img-fluid coverart"
                    draggable="false"
                />
            </figure>
        </div>
        <div class="col-6 col-md-4">
            <figure class="figure pt-4 mb-0 pb-4">
                <img
                    src={logo2}
                    alt="Logo de Sentimental Thug"
                    class="figure-img img-fluid coverart"
                    draggable="false"
                />
            </figure>
        </div> -->
    </div>

    <div class="countdown-wrapper pt-3 pb-3">
        <Countdown />
    </div>

    <!-- <div class="coming-soon-wrapper pt-4 pb-4">
        <h1>COMING SOON</h1>
    </div> -->

    <div class="pt-4">
        {#each tracklist as track}
            <div class="tracklist">
                <div class="svelte-track-group mb-3">
                    <h5 class="trackname fs-6 mb-0 text-uppercase">
                        0{track.id}.
                        {track.artists} - {track.title}
                    </h5>
                    {#if track.feat}
                        <p class="fs-6 m-0"><em>ft. {track.feat}</em></p>
                    {/if}
                </div>
            </div>
        {/each}
    </div>
    <div class="links-wrapper pt-4 pb-4">
        <Links />
    </div>
</main>

<style>
    .coverart {
        width: 300px
    }
</style>
