<template>
    <PostListing blog-type="shows" :tags="tags" :posts="blogs"/>
</template>

<script>
import PostListing from '@/components/PostListing.vue';

export default {
    components: {
        PostListing
    },
    mounted () {
        console.log("mounted")
        this.$axios
            .get('https://blogbackend.malavikasmenon.repl.co/posts/?post_type=shows')
            .then(response => {
                this.blogs = response.data
            })
            .then(console.log(this.blogs))
    },
    data() {
        return {
            tags: ['Romance', 'Comedy', 'Drama'],
            blogs: []
        }
    },
}
</script>
