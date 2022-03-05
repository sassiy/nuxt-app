
<template>
 <div>
  <NuxtLink to="/about">about</NuxtLink>
  <img src="/favicon.ico" > 
  <img src="~assets/images/javascript.png" > 
  <p>Nuxt.js</p>
  <p>{{this.$route.params.id}}</p>
  <li>{{ posts.title }}</li>
 </div>
</template>

<script>
  export default {
    data(){
        return{
            posts: ""
        }
    },
    async fetch(){
        const id = this.$nuxt.context.params.id 
        this.posts = await this.$axios.$get(`https://jsonplaceholder.typicode.com/posts/${id}`)
    }
    // async asyncData({ $axios, params }) {
    //   const posts = await $axios.$get(`https://jsonplaceholder.typicode.com/posts/${params.id}`)
    //   return { 
    //       posts 
    //    }
    // }
  }
</script>
