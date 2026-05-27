<script setup>
import axios from 'axios'
import { ref } from 'vue'
import { useRouter } from 'vue-router'

const router = useRouter()
const title = ref('')
const description = ref('')

const savePost = async () => {
  await axios.post('http://localhost:8080/posts', {
    title: title.value,
    description: description.value,
  })

  router.push('/posts')
}
</script>

<template>
  <section class="page">
    <h2>Agregar post</h2>

    <form class="post-form" @submit.prevent="savePost">
      <label for="title">
        Titulo
        <input id="title" v-model="title" type="text" name="title" />
      </label>

      <label for="description">
        Descripcion
        <textarea id="description" v-model="description" name="description" rows="5"></textarea>
      </label>

      <div class="form-actions">
        <RouterLink to="/posts">Regresar al listado</RouterLink>
        <button type="submit">Guardar</button>
      </div>
    </form>
  </section>
</template>
