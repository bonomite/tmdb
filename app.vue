<script setup>
const options = {
  method: "GET",
  headers: {
    accept: "application/json",
    Authorization:
      "Bearer eyJhbGciOiJIUzI1NiJ9.eyJhdWQiOiI5ZTBlM2ZlYTczNDMwMWYyMTM1YjlhYjI4YzlkOGJlNSIsIm5iZiI6MTYyODIwMDkyOS4zMjQsInN1YiI6IjYxMGM1ZmUxNzcxOWQ3MDA3MmM4MWUzMiIsInNjb3BlcyI6WyJhcGlfcmVhZCJdLCJ2ZXJzaW9uIjoxfQ.mif95Rzn8ZY45HhbXwe_NITFQzabh6YVYf36E-edT2k",
  },
}

const { data, status, error, refresh, clear } = useFetch(
  "https://api.themoviedb.org/3/movie/popular?language=en-US&page=1",
  options
)
</script>
<template>
  <!-- <pre>{{ data }}</pre> -->
  <div v-for="movie in data.results" :key="movie.id">
    <h2>{{ movie.title }}</h2>
    <img :src="'https://image.tmdb.org/t/p/w200' + movie.poster_path" />
  </div>
</template>
