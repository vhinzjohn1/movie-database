<script>
  import MovieCard from "./MovieCard.svelte";
  import SearchMovies from "../components/SearchMovies.svelte";
  export let populars;
</script>

<div class="wrapper">
  <h3>Popular Movies</h3>
  <SearchMovies />
</div>
<div class="popular-movies">
  {#each populars as popular}
    <MovieCard movie={popular} />
  {/each}
</div>

<style>
  .wrapper{
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  h3 {
    padding: 0 1rem;
  }
  .popular-movies {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    grid-column-gap: 1rem;
    grid-row-gap: 2rem;
  }
</style>
