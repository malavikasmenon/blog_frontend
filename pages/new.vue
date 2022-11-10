<template>
    <section class="main-container" v-if="isLoggedIn">
        <input type="text" class="title" v-model="title" placeholder="Enter title">
        <textarea rows="17" class="content mt-5" v-model="content" placeholder="Enter content"> </textarea>
        <select v-model="selectedType" class="mb-5 dropdown" label="Options"> 
            <option disabled value="">Please select one</option>
            <option value="books" selected>Books</option>
            <option value="movies">Movies</option>
            <option value="shows">Shows</option>
        </select>
        <br>
        <input type="text" class="mt-1" placeholder="Author? Director?" v-model="subtitle">
        <input type="text" class="mt-1" placeholder="Year of release?" v-model="year">
        <input type="text" class="mt-1" placeholder="Image Link" v-model="imgLink">
        <input type="text" class="mt-1" placeholder="Tags" v-model="tags">
        <br>
        <button v-on:click="addPost" class="btn bg-dark text-white my-5">Add Post</button>
        <p class="success-msg">{{successMessage}}</p>
    </section>
    <section class="login p-5" v-else>
        <p>You are not logged in. Please log in with admin credentials to write post</p>
        <NuxtLink to="/login"><button class="bg-dark text-white">Login</button></NuxtLink>
    </section>
</template>

<script>
    export default {
        data() {
            return {
                title: '',
                content: '',
                subtitle: '',
                year: '',
                imgLink: '',
                options: ['books', 'movies', 'shows'],
                selectedType: 'books',
                selectedTags: '',
                tags: '',
                successMessage: ''
            }
        },
        methods: {
            addPost() {
                this.$axios.post('https://blogbackend.malavikasmenon.repl.co/add-post/', {
                    'title': this.title,
                    'subtitle': this.subtitle,
                    'content': this.content,
                    'year_of_release': this.year,
                    'tags': this.tags,
                    'image_url': this.imgLink,
                    'post_type': this.selectedType,
                    'slug_field': this.title.toLowerCase().replace(' ', '-'),
                    // 'created': new Date()
                })
                    .then(response => this.successMessage = "Successfully submitted")
                    .catch(error => console.log(error))
            }
        },
        computed: {
            isLoggedIn() {
                if(process.client){
                    if(localStorage.getItem('authToken')){
                    console.log(localStorage.getItem('authToken'))
                    return true              
                    }
                }
                console.log("not logged in")
                return false
            },
        },
    }
</script>

<style scoped>
input, textarea {
    background-color: #fff2f2;
    border: 0px;
    margin-left: 5%;
    padding: 2%;
    border-bottom: 1px solid black;

}
.title {
    border-bottom: 1px solid black;
    font-family: Satisfy;
    font-size: 36px;
    width: 80%;    
}
.content {
    width: 80%;
    font-size: 24px;
    border: 1px solid grey;
    border-radius: 10px;
}

.dropdown {
    width: 200px;
}

input:focus-visible {
    /* border: 0px !important; */
    /* border: none; */
    /* outline: 1px solid grey; */
    /* outline: none; */
    /* background-color: rgb(252, 249, 251); */
    border-bottom: 1px solid black;
}

select {
    margin-left: 5%;
    margin-top: 3%;
}

.btn, .success-msg {
    margin-left: 5%;
}

</style>