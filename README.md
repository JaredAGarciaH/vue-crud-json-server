# Vue CRUD JSON Server

Proyecto realizado como parte del tutorial CRUD con Vue.js, Composition API, Vue Router y json-server.

## Descripcion

Esta aplicacion permite administrar posts mediante operaciones CRUD. El frontend esta desarrollado con Vue 3 y Vite, mientras que la API falsa se crea con json-server.

## Tecnologias utilizadas

- Vue.js 3
- Vite
- JavaScript
- Composition API
- Vue Router
- Axios
- json-server
- HTML
- CSS

## Instalacion

```bash
npm install
```

## Ejecutar el proyecto

Para probar la aplicacion completa se deben usar dos terminales.

Terminal 1:

```bash
npm run server
```

Terminal 2:

```bash
npm run dev
```

## API fake

json-server queda disponible en:

```text
http://localhost:8080/posts
```

## Rutas

- `/`
- `/posts`
- `/posts/add`
- `/posts/:id`
- `/posts/edit/:id`

## Funcionalidades

- Listar posts
- Crear posts
- Ver detalle de un post
- Editar posts
- Eliminar posts

## Scripts disponibles

```bash
npm run dev
npm run build
npm run preview
npm run server
```
