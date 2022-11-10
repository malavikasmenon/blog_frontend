<template>
    <Post :post="post" />
</template>

<script>
import Post from '@/components/Post.vue';
    
export default {
    components: {
        Post
    },
    created () {
        this.$axios
            .get("https://blogbackend.malavikasmenon.repl.co/posts/?post_type=movies")
            // .then(response => console.log(response.data))
            .then(response => {
                console.log(response.data)
                this.posts = response.data
            })
            // .then(console.log("what", this.posts))
            .then(response => this.filteredPost(this.$route.params))
    },
    data() {
        return {
            posts: [],
            post: NaN,
        }
    },
    methods: {
        filteredPost(slugField) {
            slugField = slugField['movie']
            const post = this.posts.find(el => el.slug_field == slugField)
            this.post = post
        }
    },
}
</script>
