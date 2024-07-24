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
    import logo from "../assets/sentimental-logo-1.jpeg"
    import logo2 from "../assets/sentimental-logo-2.jpeg"
</script>

<main class="text-center mt-4 container">
    <div class="row m-auto">
        <div class="col-12 col-md-4">
            <figure class="figure pt-4 mb-0 pb-4">
                <img
                    src={cover}
                    alt="Cover art de Sentimental Thug"
                    class="figure-img img-fluid coverart"
                    draggable="false"
                />
            </figure>
        </div>
        <div class="col-6 col-md-4">
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
        </div>
    </div>

    <!--
    <div class="countdown-wrapper pb-4">
        <Countdown />
    </div>
    -->

    <div class="coming-soon-wrapper pt-4 pb-4">
        <h1>COMING SOON</h1>
    </div>

    <div class="pt-4">
        {#each tracklist as track}
            <div class="tracklist text-uppercase">
                <h5 class="trackname fs-6 blurred-text">
                    0{track.id}.
                    {track.artists} -
                    {track.title}
                    <!-- <span class="blurred-text">{track.title}</span> -->
                </h5>
            </div>
        {/each}
    </div>
    <!-- <div class="links-wrapper pt-4 pb-4">
        <Links />
    </div> -->
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
        width: 300px
    }

    figure {
        filter: blur(15px);
        -webkit-filter: blur(15px);
    }

    img {
        -webkit-user-select: none;
        user-select: none !important;
        cursor: default;
    }
</style>
