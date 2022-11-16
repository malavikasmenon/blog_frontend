<template>
  <div class="main-container">
    <div class="main-heading">
      <h1>The Alternate World</h1>
      <h2>- Malavika S. Menon</h2>
      <hr>
    </div>
    <div class="main-content px-lg-5 mt-5">
      <p>
        Sometimes while scrolling through Netflix, I come across a lesser known movie and start watching it, 
        only to realise in 5 minutes that I have already seen this before. Since we consume content so regularly 
        and quickly, it's only natural that we lose track of what we've watched or forget some storylines. 
        This blog can be thought of as a type of entertainment journal, where I keep track of the content I consume, 
        be it books, shows or movies. A little journey into the world of fiction we read and watch, 
        where we look at the stories told, and the lives of the characters we observe so closely. And of course, 
        a little tribute and appreciation to all the creators who give us a chance to live an alternate life for a while. 
      </p>
      <p>
        PS: The format of these posts may vary greatly depending on my mood while writing it. 
        Some may contain spoilers, so apologies in advance if you do read it! 
      </p>
    </div>
    <div class="main-options">
      <b-card-group deck class="card-group pt-3">
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
  /* padding-top: 3%; */
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
  flex-wrap: wrap;
}
.card {
  border-radius: 20px;
  box-shadow: 0 3px 10px rgb(0 0 0 / 0.2);
  width: 400px;
}
@media (max-width:768px) {
  .card {
    width: 80%;
  }
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
