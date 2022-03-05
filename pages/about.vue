<template>
<div>
 <NuxtLink to="/">Back to Home</NuxtLink>
 <h1>about　page</h1>
 <p>シークレットキー</p>
 <p>{{ $config.SECRET_KEY }}</p>
 <h2>postデータ</h2>
<ul>
    <li v-for="post in posts" :key=post.id>
        {{post.title}}
    </li>
</ul>
<h2>usersデータ</h2>
<ul>
    <li v-for="user in users" :key=user.id>
        {{user.name}}
    </li>
</ul>
</div>
</template>

<script>
  export default {
    data(){
        return{
            posts: "",
            users: "",
        }
    },
    async fetch(){
        this.posts = await this.$axios.$get(`${this.$config.baseURL}/posts/`)
        this.users = await this.$axios.$get(`${this.$config.baseURL}/users/`)
    }
    // async asyncData({ $axios, $config }) {
    //   const posts = await $axios.$get(`${$config.baseURL}/posts/`)
    //   const users = await $axios.$get(`${$config.baseURL}/users/`)
    //   return { 
    //       posts,
    //       users 
    //    }
    // }
  }
</script>
