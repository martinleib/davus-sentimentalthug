<script>
    import Icon from "@iconify/svelte";
</script>

<footer class="pt-5 pb-5 text-center">
    <section class="fixed-md-bottom">
        <a href="https://open.spotify.com/intl-es/artist/2Gxaf60UDXKrmcIhEjULSk?si=bBexXolHQRaMyuYIpLZQ3w" target="_blank" class="me-3 footer-icon">
            <Icon icon="akar-icons:spotify-fill" />
        </a>
        <a href="https://www.instagram.com/davusito/" target="_blank" class="me-3 footer-icon">
            <Icon icon="akar-icons:instagram-fill" />
        </a>
        <a href="https://www.youtube.com/channel/UCQVvmfqjIy94d9z__cafdLQ" target="_blank" class="footer-icon">
            <Icon icon="akar-icons:youtube-fill" />
        </a>
    </section>
</footer>

<style>
    .footer-icon {
        font-size: 2rem;
        color: rgb(195, 130, 238);
        transition: 0.2s;
    }

    a:hover {
        color: #fff;
    }

    footer {
        z-index: 2;
    }
</style>
