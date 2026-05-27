<script setup>
import axios from 'axios'
import { onMounted, ref } from 'vue'

const posts = ref([])

const getPosts = async () => {
  const response = await axios.get('http://localhost:8080/posts')
  posts.value = response.data
}

onMounted(() => {
  getPosts()
})
</script>

<template>
  <section class="page">
    <h2>Listado de posts</h2>

    <div class="posts-list">
      <article v-for="post in posts" :key="post.id" class="post-card">
        <div class="post-content">
          <span class="post-id">ID: {{ post.id }}</span>
          <h3>{{ post.title }}</h3>
          <p>{{ post.description }}</p>
        </div>

        <div class="post-actions">
          <RouterLink :to="`/posts/${post.id}`">Ver</RouterLink>
          <RouterLink :to="`/posts/edit/${post.id}`">Editar</RouterLink>
          <button type="button">Eliminar</button>
        </div>
      </article>
    </div>
  </section>
</template>
