<script lang="ts">
  import { media } from "$lib/api";
  import type { MovieDetails } from "$lib/types";

  export let movie: MovieDetails;

  $: images = movie.images;
  $: backdrops =
    images.backdrops.find((image) => !image.iso_639_1) || images.backdrops[0];
  $: logo =
    images.logos.find((image) => image.iso_639_1 === "en") || images.logos[0];
</script>

<a href="/movie/{movie.id}">
  <img
    class="backdrop"
    src={media(backdrops.file_path, 1280)}
    alt={movie.title}
    style="aspect-ratio: {backdrops.aspect_ratio};"
  />
  <img
    class="logo"
    alt={movie.title}
    src={media(logo.file_path, 1280)}
    style="aspect-ratio: {logo.aspect_ratio};"
  />
</a>

<style>
  a {
    display: flex;
  }
  .backdrop {
    widows: 100%;
  }

  .logo {
    position: absolute;
    left: 1rem;
    top: 0;
    height: 100%;
    width: 30%;
    object-fit: contain;
    filter: drop-shadow(o o 1rem black);
  }
</style>
