<template>
    <div class="container">
      <h1 class="my-4">前台頁面</h1>
      <div class="mb-2">
        <router-link to="/" class="mx-2">Home</router-link> |
        <router-link to="/products" class="mx-2">前台產品列表</router-link> |
        <router-link to="/cart" class="mx-2">購物車</router-link>
      </div>
        
      <RouterView></RouterView>
    </div>
</template>
    
<script>
  import { RouterView } from 'vue-router'
  export default {
    components: {
      RouterView
    },
    methods: {
      logout () {
        document.cookie = `hexschoolToken=; expires=${new Date()};`
        this.$$route.push('login')
      }
    }
  }
</script>