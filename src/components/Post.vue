<template>
    <div>
        <p v-if="errorMessage">{{errorMessage}}</p>
       <button @click="getPosts">Load Posts</button>
       <div v-for="post in posts" :key="post.id">
           <h1>{{post.title}}</h1>
                      <p>{{post.body}}</p>

           <span>{{post.id}}</span>
           <hr>

       </div>
    </div>
</template>

<script>
import axios from 'axios'

    export default {
        name:"Post",
        data()
        {
            return {
                posts : [],
                errorMessage:'',
            }
        },
        methods :
        {
             getPosts()
             {
               axios.get("https://jsonplaceholder.typicode.com/posts").then((response)=>{
                   console.log(response.data)
                   this.posts =  response.data;

               }).catch((error)=>{
                   console.log(error)
                   this.errorMessage = "Eroor in Api get Request"
                   })


             }
        }
    }
</script>

<style scoped>

</style>
