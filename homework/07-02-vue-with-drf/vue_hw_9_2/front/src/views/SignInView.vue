<template>
  <div>
    <h1>로그인 페이지</h1>
    <form @submit.prevent="logIn">
      <div>
        <label for="username">username : </label>
        <input type="text" v-model.trim="username" id="username">
      </div>
      <div>
        <label for="password">password : </label>
        <input type="password" v-model.trim="password" id="password">
      </div>
      <input type="submit" value="submit">
    </form>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import { useArticleStore } from '@/stores/articles'

const username = ref(null)
const password = ref(null)

const store = useArticleStore()

const logIn = function() {
  const payload = {
    username: username.value,
    password: password.value
  }
  store.logIn(payload)
}

</script>

<style scoped>

</style>