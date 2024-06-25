<script>
  export let movie;
</script>

<div class="movie-card">
  <a href={"/movie/" + movie.id}>
    <img
      src={"https://image.tmdb.org/t/p/w500" + movie.poster_path}
      alt={movie.title}
    />
  </a>
  <div class="description">
    <h2>{movie.title}</h2>
    <p>{movie.release_date}</p>
  </div>
</div>

<style>
  .movie-card {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 1rem;
  }

  img {
    width: 100%;
    border-radius: 1rem;
  }

  .description {
    text-align: center;
  }

  h2 {
    font-size: 1.1rem;
    margin-bottom: 0.5rem;
  }

  p {
    font-size: 0.9rem;
    margin: 0;
  }
</style>
