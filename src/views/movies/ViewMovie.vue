<template>
  <div>
      <h1 style="padding:0; margin:0; border-bottom: 1px solid #aaa; text-transform:capitalize">{{movie.title}}</h1>
      <div class="w3-panel w3-sand w3-leftbar">
          <p>{{movie.year}} | {{movie.cast}}</p>
      </div>
      <p>
          {{movie.synopsis}}
      </p>
  </div>
</template>

<script>
export default {
    props: ['id'],
    data() {
        return {
            movie: {}
        }
    },
    mounted() {
        fetch('http://localhost:8000/api/movies/' + this.id)
        .then(res=>res.json())
        .then(data=>this.movie=data)
    }
}
</script>

<style>

</style>