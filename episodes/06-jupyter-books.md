---
title: Páginas GitLab con libros Jupyter
teaching: 0
exercises: 0
---

::::::::::::::::::::::::::::::::::::::: objectives

- Publish Jupyter notebooks as HTML on the web with GitHub Pages

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: questions

- How do I publish web pages through GitLab and Jupyter books?

::::::::::::::::::::::::::::::::::::::::::::::::::

Hagamos algo diferente, que te sonará un poco más familiar si estás acostumbrado a los
proyectos [Jupyter](https://jupyter.org/). De su sitio web:

> El Proyecto Jupyter existe para desarrollar software de código abierto, estándares
> abiertos y servicios para la computación interactiva en docenas de lenguajes de
> programación.

**Los cuadernos Jupyter** te permiten crear y compartir documentos que contienen código
en vivo, así como texto narrativo. **Jupyter Lab** amplía sus funcionalidades creando un
entorno de desarrollo interactivo (que le permite navegar por su sistema de archivos y
definir el entorno de codificación). **Jupyter Hub** es una versión multiusuario de
Jupyer Lab que las instituciones pueden implementar localmente ([como hicimos en EMBL](https://jupyterhub.embl.de/)).

¿Y **Libro de Jupyer**?

> Jupyter Book es un proyecto de código abierto para crear libros y documentos
> atractivos y de calidad editorial a partir de material computacional.

El [tutorial extenso](https://jupyterbook.org/start/your-first-book.html) te guiará a
través de los pasos de instalación y la personalización detallada disponible, en el
contexto de esta lección vamos a cubrir sólo lo básico. Lo primero es lo primero, vamos
a instalar Jupyter Book. En tu terminal:

```bash 
pip install -U jupyter-book
```

> 
Ten en cuenta: necesitarás tener **pip** instalado también. Ahora, vamos a crear nuestro
primer proyecto de libro. El comando `jupyter-book --help` nos ayudaría a comprobar las
opciones aquí, pero en esta lección haremos spoiler de algo: el comando

```bash 
jupyter-book create jupyter-book-demo
```

> 
el comando creará un libro Jupyter básico en una carpeta `jupyter-book-demo`. Esta
carpeta ya incluye las tres cosas necesarias para construir un libro: un archivo
`_config.yml`, una tabla de contenido `_toc.yml` y el contenido del libro en una
colección de archivos MarkDown, reStructuredText o Jupyter Notebook.

Como nos estamos cansando de tanto desarrollo y despliegue, no queremos editar nada del
contenido, pero en su lugar priorizamos tenerlo funcionando en GitLab. Adivina, ¿qué
necesitamos añadir? Un archivo `.gitlab-ci.yml` de hecho.

```yaml 
pages:
  stage: deploy
  image: python:slim
  script:
    - pip install -U jupyter-book
    - jupyter-book clean .
    - jupyter-book build .
    - mv _build/html public
  artifacts:
    paths:
      - public
```

> 
Este trozo de código:

1. Instala jupyter-book (o comprueba que está correctamente instalado de forma remota).
2. Limpia la carpeta de archivos resultantes de (eventuales) construcciones previas.
3. ejecuta el comando `jupyter-book build .`, que construye el libro en la carpeta en
  una subcarpeta `_build`. Puedes comprobar la salida ejecutando el mismo comando en tu
  terminal, y te darás cuenta de que los archivos HTML reales están en la subcarpeta
  `_build/html`.
4. A continuación, mueve el contenido HTML a nuestra carpeta habitual `public` donde se
  almacenan los artefactos.

:::::::::::::::::::::::::::::::::::::::  challenge

## Tu tiempo para experimentar con una plantilla

Esta plantilla es deliberadamente mínima para darte la oportunidad de poner a prueba
tus habilidades de lectura de documentación. Consulta las guías temáticas en
[jupyterbook.org](https://jupyterbook.org/intro.html) y encuentra la manera de:

1. Añade otra página llamada "Acerca de" y enlazada desde la tabla de contenidos.
2. Juega con el formato de archivo de esta nueva página, añade el mismo tipo de
  contenido en formatos MarkDown, reStructuredTex y Notebook.
3. Añade una figura y un pie de figura.
4. Inserta una celda de código. Si estás familiarizado con algún lenguaje de
  programación, añade un trazado sencillo y visualiza la salida de dicho trazado en
  tu página.
5. Para funciones de código más avanzadas, consulta [cómo hacer que el código sea ejecutable](https://jupyterbook.org/interactive/thebe.html)
6. ¡Inspírate en la [galería de libros Jupyter](https://executablebooks.org/en/latest/gallery.html)!

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: keypoints

- Through Jupyter books, you'll be able to integrate interactive components and code in your web pages

::::::::::::::::::::::::::::::::::::::::::::::::::


