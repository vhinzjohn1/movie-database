<script>
  import { page } from "$app/stores";
  import { onMount } from "svelte";

  let movieId;
  let movieDetail = [];

  onMount(async () => {
    movieId = $page.params.slug;

    const response = await fetch(
      `https://api.themoviedb.org/3/movie/${movieId}?api_key=3f73f87b7f82abdc494b12439b551e03&language=en-US`
    );
    const data = await response.json();
    movieDetail = data;
  });
</script>

<div class="movie-details">
  <div class="img-container">
    <img
      src={"https://image.tmdb.org/t/p/original" + movieDetail.backdrop_path}
      alt={movieDetail.title}
    />
  </div>
  <div class="txt-container">
    <h1>{movieDetail.title}</h1>
    <p class="overview">{movieDetail.overview}</p>

    <p>
      <span>Release Date: </span>
      {movieDetail.release_date} <br />
      <span>Budget: </span>
      {movieDetail.budget} <br />
      <span>Rating: </span>
      {movieDetail.vote_average} <br />
      <span>Runtime:</span>
      {movieDetail.runtime}mins
    </p>
  </div>
</div>

<style>
  @import url("https://fonts.googleapis.com/css?family=Catamaran:400,800");
  * {
    font-family: "Catamaran", sans-serif;
  }
  h1 {
    padding: 1rem 0rem 2rem;
  }
  p {
    padding: 1rem 0rem;
  }
  .img-container {
    width: 100%;
  }
  img {
    width: 100%;
    border-radius: 1rem;
  }
  .movie-details {
    margin: 2rem 20%;
  }
  span {
    font-weight: bold;
  }
</style>
