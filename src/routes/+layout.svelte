<script>
    import '../styles.css'
    import logo from '$lib/images/logo.svg'
    import tmbd from '$lib/images/tmdb.svg'
</script>

<nav>
    <a href="/"> 
     <img alt='SvelteFlix' src={logo}/>
    </a>
    
    <div class='links'>
        <a href="/search">Search</a>
        <a href="/watchlist">Watchlist</a>
        <a href="/login">Log In</a>
    </div>
</nav>

<main>
    <slot>
    
    </slot>
</main>

<footer>
    <p> Data Provided By</p>
    <a href="https://developer.themoviedb.org/docs/getting-started">
        <img alt='tmbd' src={tmbd}/>
    </a>
</footer>

<style>
    nav {
        display: flex;
        width: 100%;
        height: 3rem;
        align-items: center;
        justify-content: space-between;
        max-width: var(--column);
        padding: 0 var(--side);
        color: var(--accent)
    }

    a {
        color: rgb(151, 21, 21);
        text-decoration: none;
    }

    img {
        height: 1rem;
    }

    .links {
        display: flex;
        gap: 1rem;
    }

    footer {
        display: flex;
        justify-content: center;
        height: 5rem;
    }
</style>