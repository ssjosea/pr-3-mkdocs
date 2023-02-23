# Bienvenido a la web de Jose A. Estrella Tijeras alojada en GitHub Pages
La web está alojada en -> [mkdocs.org](https://www.mkdocs.org).

## ¿Qué es MkDocs?

MkDocs es un generador de sitios web estáticos que nos permite crear de forma sencilla un sitio web para documentar un proyecto. El contenido del sitio web está escrito en texto plano en formato Markdown y se configura con un único archivo de configuración en formato YAML.

En esta práctica vamos a utilizar una imagen Docker que contiene MkDocs y el theme Material.

Esta imagen **Docker** nos permite:

- Crear un **nuevo proyecto** (Comando: `new`).
- Crear un servidor de desarrollo local (Comando: `serve`).
- Generar la documentación (Comando: `build`).
- Publicar la documentación en GitHub Pages (Comando: `gh-deploy`).

```
Usage: mkdocs [OPTIONS] COMMAND [ARGS]...

  MkDocs - Project documentation with Markdown.

Options:
  -V, --version  Show the version and exit.
  -q, --quiet    Silence warnings
  -v, --verbose  Enable verbose output
  -h, --help     Show this message and exit.

Commands:
  build      Build the MkDocs documentation
  gh-deploy  Deploy your documentation to GitHub Pages
  new        Create a new MkDocs project
  serve      Run the builtin development server
```

## Comandos

### Comando: `new`

```
docker run --rm -it -p 8000:8000 -v "$PWD":/docs squidfunk/mkdocs-material new .
```

### Comando: `serve`

```
docker run --rm -it -p 8000:8000 -v "$PWD":/docs squidfunk/mkdocs-material
```

### Comando: `build`

```
docker run --rm -it -v "$PWD":/docs squidfunk/mkdocs-material build
```

### Comando:` gh-deploy`

```
docker run --rm -it -v ~/.ssh:/root/.ssh -v "$PWD":/docs squidfunk/mkdocs-material gh-deploy
```