<template>
  <main class="app">
    <header class="header">
      <div>
        <h1>CRUD de Posts con Vue</h1>
        <p>Vue 3 + Composition API + Vue Router + json-server</p>
      </div>

      <nav class="nav">
        <RouterLink to="/">Inicio</RouterLink>
        <RouterLink to="/posts">Posts</RouterLink>
        <RouterLink to="/posts/add">Agregar post</RouterLink>
      </nav>
    </header>

    <RouterView />
  </main>
</template>
