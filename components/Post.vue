<template>
    <section class="main-container" v-if="post">
        <header class="main-heading mt-5">
            <span class="m-lg-auto text-heading">
                <h1 class="mt-sm-2">{{post.title}}</h1>
                <h4 class="mt-3">{{post.subtitle}} | {{post.year_of_release}}</h4>
            </span>
            <img :src="post.image_url" class="image" height="300px"/>
        </header>
        <!-- <hr /> -->
        <article class="main-content p-3">
            <p class="mt-3 article">
                {{post.content }}
            </p>
        </article>
    </section>
</template>

<script>
    export default {
        props: {
            post: Object,
            default: {}
        }
    }
</script>

<style scoped>
.main-container {
  /* border: 1px solid black; */
}
.main-heading {
  text-align: center;
  /* padding-top: 3%; */
  display: flex;
  justify-content: space-between;
  align-items: center;
  max-width: 50%;
  margin: auto;
  border-radius: 20px;
  box-shadow: 0 3px 10px rgb(0 0 0 / 0.2);
  flex-wrap: wrap-reverse;
  /* align-self: center; */
  /* border: 2px solid black; */
}
@media (max-width:768px) {
.main-heading {
    margin: auto;
    /* border: 1px solid black; */
    min-width: 80%;
    padding: 5%;
  }
.text-heading {
    min-width: 100% !important;
    margin: 0;
    /* border: 1px solid black; */
  
}
h1 {
        margin-top: 5%;
    }
.image {
    min-width: 80%;
    margin: auto;
}
}
.image {
    border-top-right-radius: 20px;
    border-bottom-right-radius: 20px;
}
hr {
    margin-top: 0;
}
.main-content {
  /* border: 1px solid black; */
  margin-left: 5%;
  margin-right: 5%;
  font-size: 24px;
  /* opacity: 0.8; */
  text-align: center;
  flex-direction: row;
}
.main-options {
  text-align: center;
}
.article {
    text-align: justify;
    /* max-width: 80%; */
    /* overflow-x: scroll; */
    /* white-space: pre; */
    line-break: strict;
    white-space: pre-line;
}

pre {
    max-width: 80%;
    overflow-wrap: normal;
    overflow-x:initial;
    width: 500px

}

</style>