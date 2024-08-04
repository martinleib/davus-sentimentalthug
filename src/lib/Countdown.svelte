<script>
    import { onMount } from "svelte";
    import { writable } from "svelte/store";

    let countdownDate = new Date("Aug 16, 2024 00:00:00").getTime();
    let days = writable(0);
    let hours = writable(0);
    let minutes = writable(0);
    let seconds = writable(0);

    function formatUnit(unit) {
        return String(unit).padStart(2, '0');
    }

    function updateCountdown() {
        let currentDate = new Date().getTime();
        let t = countdownDate - currentDate;

        if (t > 0) {
            days.set(Math.floor(t / (1000 * 60 * 60 * 24)));
            hours.set(Math.floor((t % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60)));
            minutes.set(Math.floor((t % (1000 * 60 * 60)) / (1000 * 60)));
            seconds.set(Math.floor((t % (1000 * 60)) / 1000));
        } else {
            days.set(0);
            hours.set(0);
            minutes.set(0);
            seconds.set(0);
        }
    }

    onMount(() => {
        updateCountdown();
        const interval = setInterval(updateCountdown, 1000);

        return () => {
            clearInterval(interval);
        };
    });
</script>

<div class="countdown">
    <h2>
        {$days}:{formatUnit($hours)}:{formatUnit($minutes)}:{formatUnit($seconds)}
    </h2>
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
