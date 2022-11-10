<template>
    <PostListing blog-type="books" :tags="tags" :posts="blogs"/>
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
            .get('https://blogbackend.malavikasmenon.repl.co/posts/?post_type=books')
            .then(response => {
                this.blogs = response.data
            })
            .then(console.log(this.blogs))
    },
    data() {
        return {
            tags: ['Romance', 'Comedy', 'Drama'],
            // blogs: [
            //     {
            //         'title': 'It Ends With Us',
            //         'image': 'books.jpg',
            //         'url': 'it-ends-with-us'
            //     },
            //     {
            //         'title': 'Atomic Habits'
            //     },
            //     {
            //         'title': 'Invisible Women'
            //     },
            //     {
            //         'title': 'It Ends With Us'
            //     },
            //     {
            //         'title': 'Atomic Habits'
            //     },
            //     {
            //         'title': 'Invisible Women'
            //     }
            // ]
            blogs: []
        }
    },
}
</script>
