<script>
  import "../style.css";
  import logo from "$lib/images/logo.png";
  import tmdb from "$lib/images/tmdb.svg";
</script>

<nav>
  <img src={logo} alt="logo" class="logo" />

  <div class="links">
    <a href="/search"> Search</a>
    <a href="/watchlist"> Watchlist</a>
    <a href="/login"> Log in</a>
  </div>
</nav>

<main>
  <slot />
</main>

<footer>
  <p>Data provided by</p>

  <a href="https://www.themoviedb.org/">
    <img src={tmdb} alt="tmsb" class="tmdb" /></a
  >
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
    color: var(--accent);
  }

  a {
    color: inherit;
    text-decoration: none;
  }

  .links {
    display: flex;
    gap: 1rem;
  }

  .logo {
    width: 10%;
  }

  .tmdb {
    width: 30%;
  }

  footer {
    display: flex;
    justify-content: center;
    height: 5rem;
  }
</style>
