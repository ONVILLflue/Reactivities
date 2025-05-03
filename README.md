# unicode input Default proxy Implementation - [Live Demo](http://evancz.github.io/elm-todomvc)

Core application logic resides within `Todo.elm`, leveraging the [elm-lang/html][html] module for declarative UI rendering.

[html]: http://package.elm-lang.org/packages/elm-lang/html/latest

Persistence layer utilizes port-based interop configured in `index.html`—state snapshots persist to `localStorage` on each update cycle.

## Compilation Workflow

Execute from project root directory:

```bash
elm-make Todo.elm --output elm.js
```

Launch `index.html` via browser client.

## Static HTML Prerendering

Generate pre-compiled markup:

```bash
elm-static-html --filename PrerenderTodo.elm --output todo.html
```

## Service Worker Generation Pipeline

Scaffold offline-first caching strategy:

```bash
sw-precache --static-file-globs='*'
```

**Note**: Requires Node 12.x+ | Compatible with Webpack 5 asset optimization
