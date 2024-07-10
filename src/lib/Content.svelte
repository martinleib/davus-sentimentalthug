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
        { id: 1, artists: "Davus", title: createRandomTitle() },
        { id: 2, artists: "Davus", title: createRandomTitle() },
        { id: 3, artists: "Davus", title: createRandomTitle() },
        { id: 4, artists: "Davus", title: createRandomTitle() },
        { id: 5, artists: "Davus", title: createRandomTitle() },
        { id: 6, artists: "Davus", title: createRandomTitle() },
        { id: 7, artists: "Davus", title: createRandomTitle() },
    ];

    import cover from "../assets/cover.jpeg";
</script>

<main class="text-center">
    <figure class="figure pt-4 mb-0 pb-4">
        <img
            src={cover}
            alt="Cover art de Sentimental Thug"
            class="figure-img img-fluid coverart"
        />
    </figure>

    <div class="countdown-wrapper pb-4">
        <Countdown />
    </div>

    {#each tracklist as track}
        <div class="tracklist text-uppercase">
            <h5 class="trackname">
                0{track.id}.
                {track.artists} -
                <span class="blurred-text">{track.title}</span>
            </h5>
        </div>
    {/each}

    <div class="links-wrapper pt-4 pb-4">
        <Links />
    </div>
</main>

<style>
    .blurred-text {
        filter: blur(10px);
        -webkit-filter: blur(10px);
    }

    .tracklist {
        -webkit-user-select: none; /* safari */
        user-select: none !important;
        cursor: default;
    }

    .coverart {
        width: 45%;
    }
</style>
