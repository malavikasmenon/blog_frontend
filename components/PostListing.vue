<template>
    <div class="main-container">
        <div class="main-heading">
            <h1>The World of {{blogType}}</h1>
        </div>
        <hr />
        <div class="main-content">
            <b-dropdown text="Categories" variant="outline-dark" class="m-2">
                <b-dropdown-item v-for="tag in tags">{{tag}}</b-dropdown-item>
            </b-dropdown> 
            <b-card-group deck class="card-group pt-5">
                <div v-for="blog in posts">
                    <NuxtLink :to="`${blogType}/${blog.slug_field}`">
                        <b-card class="card mx-5 mb-5" :title="blog.title" :img-src="blog.image_url" img-height="250" img-alt="Movies" img-top>
                        </b-card>
                    </NuxtLink>
                </div>
            </b-card-group>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        posts: {
            type: Array,
            default: [] 
        },
        tags: {
            type: Array,
            default: []
        },
        blogType: {
            type: String,
            default: 'Movies'
        }
    },
}
</script>



<style scoped>
.main-heading {
  text-align: center;
  padding-top: 3%;
}
.main-content {
  /* border: 1px solid black; */
  margin-left: 5%;
  margin-right: 5%;
  font-size: 24px;
  text-align: center;
}
.card-group {
  /* max-width: 80%; */
  margin-left: 5%;
  margin-right: 5%;
  display: flex;
  justify-content: center;
}
.card {
  border-radius: 20px;
  box-shadow: 0 3px 10px rgb(0 0 0 / 0.2);
  width: 350px;
}
</style>