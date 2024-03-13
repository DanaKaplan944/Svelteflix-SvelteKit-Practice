<script lang="ts">
  import { media } from "$lib/api";
import type { MovieListResult } from "$lib/types";
  import type { View } from "$lib/views";

    export let movies: MovieListResult[];
    export let view: View; 
    export let href: string; 

</script>

<h2 class='column'>
    {view.title}
    {#if href}<a {href}>see all</a>{/if}
</h2>

<div class='carousel'>
    {#each movies as movie}
    <a href="/movie/{movie.id}">
        <img alt={movie.title} src={media(movie.poster_path, 500)}/>

    </a>
        
    {/each}

</div>

<style>
.carousel {
		display: flex;
		height: 15rem;
		overflow-x: auto;
		overflow-y: hidden;
		white-space: nowrap;
		overscroll-behavior-x: contain;
		scroll-snap-type: x mandatory;
		gap: 1rem;
	}

	.carousel::-webkit-scrollbar {
		display: none;
	}

	h2 {
		font-size: 2.4rem;
		margin-top: 4rem;
	}

	h2 a {
		padding-left: 0.7rem;
		color: rgb(151, 21, 21);
		font-size: 1.6rem;
	}

	a {
		scroll-snap-align: start;
		height: 100%;
		aspect-ratio: 2 / 3;
	}

	img {
		width: 100%;
	}
</style>