<script>
  import PopularMovies from "../components/PopularMovie.svelte";
  import { onMount } from "svelte";
  import { fly } from "svelte/transition";
  let popular = [];
  onMount(async () => {
    const response = await fetch(
      "https://api.themoviedb.org/3/movie/popular?api_key=3f73f87b7f82abdc494b12439b551e03&language=en-US&page=1"
    );
    const data = await response.json();
    popular = data.results;
  });
</script>

<section in:fly={{ y: 50, duration: 500 }} out:fly={{ y: 50, duration: 500 }}>
  <PopularMovies populars={popular} />
</section>

<style>
  @import url("https://fonts.googleapis.com/css?family=Catamaran:400,800");
  * {
    font-family: "Catamaran", sans-serif;
  }
</style>
