<script lang='ts'>
  import Carousel from "$lib/components/Carousel.svelte";
import Hero from "./Hero.svelte";
  import { views } from "$lib/views";
    export let data; 
    console.log(data)
</script>

<h1 class='column'>Top Trending Movies</h1>

<Hero movie={data.featured}/>

<Carousel movies={data.trending.results} view={views.trending} href='/movie/trending'/>

<Carousel movies={data.now_playing.results} view={views.now_playing} href='/movie/now_playing'/>

<Carousel movies={data.upcoming.results} view={views.upcoming} href='/movie/upcoming'/>