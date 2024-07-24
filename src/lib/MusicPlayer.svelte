<script>
    import music from "../assets/background.mp3";

    const playMusic = () => {
        const audio = document.querySelector("audio");
        audio.play();
    };

    const stopMusic = () => {
        const audio = document.querySelector("audio");
        audio.pause();
    };
</script>

<audio>
    <source src={music} type="audio/mpeg" />
</audio>

<div class="musicplayer d-none d-md-flex">
    <button on:click={playMusic} class="btn btn-dark btn-play">
        <i class="fa-solid fa-play"></i>
    </button>
    <button on:click={stopMusic} class="btn btn-dark btn-stop">
        <i class="fa-solid fa-stop"></i>
    </button>
</div>

<style>
    .musicplayer {
        z-index: 10;
        display: flex;
        position: fixed;
        bottom: 0;
        right: 0;
        margin-right: 1rem;
        margin-bottom: 1rem;
        width: 100px;
        justify-content: center;
        background-color: #222;
        border-radius: 50px;
    }

    .btn-dark {
        background-color: #222 !important;
    }
    i {
        transition: 0.15s;
    }

    i:hover {
        cursor: pointer;
        color: rgb(195, 130, 238);
    }
</style>
