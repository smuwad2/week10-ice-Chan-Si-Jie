<script>
    // Import BlogPost component
    import BlogPost from './subcomponents/BlogPost.vue';
    import blogPost from './subcomponents/BlogPost2.vue'
	import axios from 'axios'
    export default {
        components: {BlogPost, blogPost},
        data() {
            return {
                posts: [
                ] // array of post objects
            }  
        },
        computed: {
            baseUrl() {
                if (window.location.hostname=='localhost')
                    return 'http://localhost:3000' 
                else {
                    const codespace_host = window.location.hostname.replace('5173', '3000')
                    return `https://${codespace_host}`;
                }
            }
        },
        created() { // created is a hook that executes as soon as Vue instance is created
            axios.get(`${this.baseUrl}/posts`)
            .then(response => {
                // this gets the data, which is an array
                this.posts = response.data
                console.log(response.data)
            })
            .catch(error => {
                this.posts = [{ entry: 'There was an error: ' + error.message }]
            })
        }
    }
</script>

<template>
   <!-- TODO: make use of the 'blog-post' component to display the blog posts -->
    <BlogPost
    v-for="post in posts"
    v-bind:key="post.id"
    v-bind:subject="post.subject"
    v-bind:entry="post.entry"
    v-bind:mood="post.mood"</BlogPost>
<!-- 
    <blogPost
    v-for="post in posts"
    v-bind:key="post.id"
    v-bind:post="post"></blogPost> -->
</template>

