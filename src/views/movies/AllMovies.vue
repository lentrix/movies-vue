<template>
  <div>
      <div class="w3-row">
          <div class="w3-col m3">
              <h4>Create Movie</h4>
              <div>
                  <label for="title">Movie Title</label>
                  <input type="text" v-model="movie.title" class="w3-input w3-border">
              </div>
              <div>
                  <label for="title">Synopsis</label>
                  <textarea rows="4" v-model="movie.synopsis" class="w3-input w3-border"></textarea>
              </div>
              <div>
                  <label for="cast">Casts</label>
                  <input type="text" v-model="movie.cast" class="w3-input w3-border">
              </div>
              <div style="padding-bottom: 18px">
                  <label for="year">Year</label>
                  <input type="number" v-model="movie.year" class="w3-input w3-border">
              </div>
              <button class="w3-button w3-brown w3-hover-deep-orange">Create Movie</button>
          </div>
          <div class="w3-col m9" style="padding-left: 18px">
              <h4>List of Movies</h4>
              <table class="w3-table w3-striped w3-bordered">
                  <tr class="w3-brown">
                      <th>Title</th>
                      <th>Cast</th>
                      <th>Year</th>
                  </tr>
                  <tr v-for="movie in movies" :key="movie.id" class="w3-hover-light-gray" style="cursor:pointer" @click="openMovie(movie.id)">
                      <td style="text-transform: capitalize">{{movie.title}}</td>
                      <td>{{movie.cast}}</td>
                      <td>{{movie.year}}</td>
                  </tr>
              </table>
          </div>
      </div>
  </div>
</template>

<script>
export default {
    data() {
        return {
            movies: [],
            movie: {}
        }
    },
    methods: {
        getAllMovies() {
            fetch('http://localhost:8000/api/movies')
            .then(res=>res.json())
            .then(data=>this.movies = data.movies)
            .catch(err=>console.log(err))
        },
        openMovie(movieId) {
            this.$router.push({
                name: 'view-movie',
                params: {
                    id: movieId
                }
            })
        }
    },
    mounted() {
        this.getAllMovies()
    }

}
</script>

<style>

</style>