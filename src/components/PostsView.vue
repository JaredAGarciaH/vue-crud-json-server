<script setup>
import axios from 'axios'
import { onMounted, ref } from 'vue'
import { useRoute } from 'vue-router'

const route = useRoute()
const post = ref(null)

const getPost = async () => {
  const id = route.params.id
  const response = await axios.get(`http://localhost:8080/posts/${id}`)
  post.value = response.data
}

onMounted(() => {
  getPost()
})
</script>

<template>
  <section class="page">
    <h2>Detalle del post</h2>

    <article v-if="post" class="post-detail">
      <span class="post-id">ID: {{ post.id }}</span>
      <h3>{{ post.title }}</h3>
      <p>{{ post.description }}</p>
    </article>

    <div v-if="post" class="form-actions">
      <RouterLink to="/posts">Volver al listado</RouterLink>
      <RouterLink :to="`/posts/edit/${post.id}`">Editar</RouterLink>
    </div>
  </section>
</template>
