<template>
 <div>
  <NuxtLink to="/about">about</NuxtLink>
  <LazyList v-if="show" />
  <button v-if="!show" @click="show = true">Open List</button>
 </div>
</template>

<script>
export default {
  data(){
    return{
      show: false
    }
  }
}
</script>

<style scoped>
  p{
    color: red;
  }
</style>