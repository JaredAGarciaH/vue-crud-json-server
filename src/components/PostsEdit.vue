<script setup>
import axios from 'axios'
import { onMounted, ref } from 'vue'
import { useRoute, useRouter } from 'vue-router'

const route = useRoute()
const router = useRouter()
const title = ref('')
const description = ref('')

const getPost = async () => {
  const id = route.params.id
  const response = await axios.get(`http://localhost:8080/posts/${id}`)
  title.value = response.data.title
  description.value = response.data.description
}

const updatePost = async () => {
  const id = route.params.id

  await axios.put(`http://localhost:8080/posts/${id}`, {
    title: title.value,
    description: description.value,
  })

  router.push('/posts')
}

onMounted(() => {
  getPost()
})
</script>

<template>
  <section class="page">
    <h2>Editar post</h2>

    <form class="post-form" @submit.prevent="updatePost">
      <label for="title">
        Titulo
        <input id="title" v-model="title" type="text" name="title" />
      </label>

      <label for="description">
        Descripcion
        <textarea id="description" v-model="description" name="description" rows="5"></textarea>
      </label>

      <div class="form-actions">
        <RouterLink to="/posts">Volver al listado</RouterLink>
        <button type="submit">Actualizar</button>
      </div>
    </form>
  </section>
</template>
