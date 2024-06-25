<script>
  import { onMount } from "svelte";
  onMount(async () => {
    const response = await fetch("https://imdb-top-100-movies.p.rapidapi.com", {
      method: "GET",
      headers: {
        "x-rapidapi-host": "imdb-top-100-movies.p.rapidapi.com",
        "x-rapidapi-key": "1f08c91f64mshf91b470b89dc697p13eba9jsn4451868a65b6",
      },
    });
    const data = await response.json();
    console.log(data);
  });
</script>

<h1>About test Page</h1>
