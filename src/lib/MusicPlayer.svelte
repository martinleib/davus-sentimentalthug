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

<div class="musicplayer">
    <button on:click={playMusic} class="btn btn-dark btn-play">
        <i class="fa-solid fa-play"></i>
    </button>
    <button on:click={stopMusic} class="btn btn-dark btn-stop">
        <i class="fa-solid fa-stop"></i>
    </button>
</div>

<style>
    .musicplayer {
        display: flex;
        position: fixed;
        bottom: 0;
        right: 0;
        width: 100px;
        justify-content: center;
        background-color: #111;
        border-radius: 5px;
    }
</style>
