<template>
  <div class="main-container">
    <div class="main-heading">
      <h1>The Fictional World</h1>
      <h2>- Malavika S. Menon</h2>
      <hr></hr>
    </div>
    <div class="main-content px-5 mt-5">
      <p>
        A little journey into the world of fiction we read and watch, where we look at the stories told, 
        and the lives of the characters we watch so closely. And of course, a little tribute and 
        appreciation to all the creators who give us a chance to live someone else's life for a while. 
        As a special bonus,  this blog can be thought of as a type of entertainment journal, 
        where I keep track of the content I consume regularly. 
      </p>
    </div>
    <div class="main-options">
      <b-card-group deck class="card-group pt-5">
        <NuxtLink to="/movies">
          <b-card class="mx-3 card" title="Movies" img-src="movies.jpg" img-height="350" img-alt="Movies" img-top>
          </b-card>
        </NuxtLink>
        <NuxtLink to="/shows">
          <b-card class="mx-5 card" title="Shows" img-src="shows.jpg" img-height="350" img-alt="Shows" img-top>
          </b-card>
        </NuxtLink>
        <NuxtLink to="/books">
          <b-card class="mx-3 card" title="Books" img-src="books.jpg" img-height="350" img-alt="Books" img-top>
          </b-card>
        </NuxtLink>
      </b-card-group>
    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage'
}
</script>

<style scoped>
.main-container {
  /* border: 1px solid black; */
}
.main-heading {
  text-align: center;
  padding-top: 3%;
}
.main-content {
  /* border: 1px solid black; */
  margin-left: 5%;
  margin-right: 5%;
  font-size: 24px;
  opacity: 0.8;
  text-align: center;
}
.main-options {
  text-align: center;
}
.card-group {
  max-width: 80%;
  margin-left: 10%;
  margin-right: 10%;
  display: flex;
  justify-content: center;
}
.card {
  border-radius: 20px;
  box-shadow: 0 3px 10px rgb(0 0 0 / 0.2);
  width: 400px;
}
a {
  color: black;
  text-decoration: none;
}
a:hover {
  color: black;
  text-decoration: none;
}
</style>
