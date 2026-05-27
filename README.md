# vue-crud-json-server

Proyecto base creado con Vue 3 y Vite para una futura aplicacion CRUD.

## Tecnologias iniciales

- Vue 3
- Vite
- JavaScript
- npm

## Instalacion

```bash
npm install
```

## Desarrollo

```bash
npm run dev
```

Para probar el listado de posts, corre dos terminales:

Terminal 1:

```bash
npm run server
```

Terminal 2:

```bash
npm run dev
```

Ya se puede crear un post desde la ruta:

```text
/posts/add
```

Ya se puede ver el detalle de un post desde:

```text
/posts/:id
```

Ya se puede editar un post desde:

```text
/posts/edit/:id
```

## API fake

Para levantar json-server:

```bash
npm run server
```

La API queda disponible en:

```text
http://localhost:8080/posts
```
