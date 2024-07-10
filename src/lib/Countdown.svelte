<script>
    import { onMount, onDestroy } from "svelte";

    let countdownDate = new Date("Aug 15, 2024 19:37:00").getTime();
    let days, hours, minutes, seconds;

    function updateCountdown() {
        let currentDate = new Date().getTime();
        let t = countdownDate - currentDate;
        days = Math.floor(t / (1000 * 60 * 60 * 24));
        hours = Math.floor((t % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
        minutes = Math.floor((t % (1000 * 60 * 60)) / (1000 * 60));
        seconds = Math.floor((t % (1000 * 60)) / 1000);
    }

    onMount(() => {
        const interval = setInterval(updateCountdown, 1000);

        return () => {
            clearInterval(interval);
        };
    });

    updateCountdown();
</script>

<div class="countdown">
    <h2>{days}:{hours}:{minutes}:{seconds}</h2>
</div>

<style>
    @media (max-width: 767px) {
        h2 {
            font-size: 2rem !important;
        }
    }

    @media (min-width: 768px) {
        h2 {
            font-size: 5rem !important;
        }
    }
</style>
