<script>
    import { page } from '$app/stores'
    import '../styles.css'
    import logo from '$lib/images/logo.svg'
    import tmbd from '$lib/images/tmdb.svg'
</script>

<nav>
    <a href="/"> 
     <img alt='SvelteFlix' src={logo}/>
    </a>
</nav>

<main class:infinite={$page.data.infinite}>
    <slot>
    
    </slot>
</main>

<footer>
	<p>
		Data provided by <a href="https://www.themoviedb.org/"><img alt="The Movie DB" src={tmbd} /></a>
	</p>
</footer>

<style>
    nav {
        display: flex;
        width: 100%;
        height: 5rem;
        align-items: center;
    }

    a {
        color: rgb(151, 21, 21);
        text-decoration: none;
    }

    img {
        height: 2rem;
        padding-top: 1rem; 
    }


    footer {
        display: flex;
        justify-content: center;
        height: 5rem;
    }

    main.infinite {
        height: 0;
        flex: 1;
        overflow: hidden;
    }

    
</style>