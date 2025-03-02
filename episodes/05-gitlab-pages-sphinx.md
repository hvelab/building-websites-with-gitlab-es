---
title: Páginas GitLab con Sphinx
teaching: 0
exercises: 0
questions:
- How do I publish web pages through GitLab and Sphinx?
objectives:
- Publish reStructuredText files as HTML on the web with GitHub Pages
keypoints:
- Through Sphinx, GitLab serves pages are generated from `.rst` files
---


[Sphinx](https://www.sphinx-doc.org/en/master/) es una herramienta para generar páginas
web o PDF, principalmente diseñada para crear la documentación de un proyecto. Fue
creada originalmente para la documentación de Python, pero tiene excelentes facilidades
para la documentación de proyectos de software en una gama de lenguajes. Los sistemas de
documentación políglotas pueden ser muy útiles en caso de que tu proyecto aumente en
complejidad o número de colaboradores, así que toma nota al respecto.

En este capítulo de la lección utilizaremos el lenguaje de programación Python. Aunque
no sea estrictamente necesario, te sugerimos que te familiarices con Python, ya que
explicarlo queda fuera del propósito de esta lección. Puedes optar por hacerlo repasando
la lección de Las Carpinterías [Programando con
Python](https://swcarpentry.github.io/python-novice-inflammation/).

> ## Ejercicio: Documentación
> En un grupo, haz que cada miembro abra la documentación de uno de los siguientes
> paquetes
> - [pytest](https://docs.pytest.org/en/latest/)
> - [seaborn](https://seaborn.pydata.org/)
> - [numpy](https://docs.scipy.org/doc/numpy/reference/)
> - [scipy-cookbook](https://scipy-cookbook.readthedocs.io/)
> - [scikit-learn](http://scikit-learn.org/stable/)
>
> Discutir cuáles son los componentes comunes, lo que es útil acerca de estos sitios de
> documentación, la forma en que abordan los conceptos generales sobre la documentación,
> cómo son similares y cómo son diferentes.
>
{: .challenge}

Mientras que Jekyll convierte archivos Markdown (`.md`) en HTML, Sphinx convierte
archivos reStructureText (`.rts`). Si bien estos dos formatos pueden parecer muy
similares a primera vista, fueron creados para dos propósitos diferentes: Markdown para
escribir para la web, reStructuredText para escribir documentación. [Esta entrada de blog](https://www.zverovich.net/2016/06/16/rst-vs-markdown.html) proporciona más
información sobre lo que esto significa en la práctica. El punto más importante que nos
gustaría destacar en este contexto es que reStructuredText también es adecuado para la
conversión a PDF. Esto lo convierte en una herramienta útil también para el desarrollo
de documentos que pueda necesitar tanto en línea como en copias en papel, por ejemplo
materiales de formación o la agenda de una reunión.

> ## Inicio rápido de Sphinx
> En aras de la claridad, los próximos pasos de este capítulo sólo se centrará en los
> archivos Sphinx que son relevantes para la generación de archivos HTML. Sin embargo,
> instalando Sphinx localmente puede ejecutar el comando quickstart para iniciar un
> proyecto básico de Sphinx. Recomendamos encarecidamente esta opción si desea ampliar
> su comprensión de cómo documentar con Sphinx. Para ello, informamos aquí de los pasos
> necesarios.
>
> Su sistema probablemente tiene Sphinx ya instalado. Compruebe si es así escribiendo en
> su terminal:
>
> ~~~
> sphinx-build --version
> ~~~
> {: .language-bash }
>
> Si no lo está, podrás instalarlo escribiendo:
>
> ~~~
> pip install -U sphinx
> ~~~
> {: .language-bash }
>
> O consulte las instrucciones de instalación más detalladas
> [aquí](https://www.sphinx-doc.org/en/master/usage/installation.html). Una vez que
> Sphinx está instalado, podemos ejecutar el comando quickstart para obtener una visión
> general del conjunto mínimo de archivos que son necesarios para construir la
> documentación. El siguiente comando creará un repositorio vacío y ejecutar este
> comando allí:
>
> ~~~
> mkdir sphinx-quickstart-test
> cd sphinx-quickstart-test
> sphinx-quickstart
> ...
> Separate source and build directories (y/n) [n]:
> ...
> Project name: My project
> Author name(s): <Your name>
> Project release []:
> ...
> Project language [en]:
> ~~~
> {: .language-bash }
>
> Se generarán varios documentos. Aquí un resumen:
>
> ![Sphinx quickstart](../fig/sphinx-quickstart.png){: .image-with-shadow width="600px"
> }
>
> Los archivos que son relevantes para nosotros en este contexto son el archivo
> `index.rst` - que es el equivalente a nuestro archivo `index.md` en el ejemplo con
> Jekyll - y el archivo `conf.py`. Esta es la razón por la que la lección sólo pasa por
> ellos.
>
{: .callout}

Crea una carpeta de proyecto vacía. Vamos a inicializar nuestro archivo `index.rst` en
la carpeta raíz de nuestro proyecto.

~~~
.. this is a comment, it is not rendered

Sphinx Example Project's documentation
======================================

Contents:

.. toctree::
    :maxdepth: 2
~~~
>
{: .language-markdown }

Reporta el encabezado principal de nuestro proyecto, y luego una tabla de contenidos a
través del "árbol TOC". Se puede dar una opción numérica maxdepth (nosotros la
initalizamos en 2) para indicar la profundidad del árbol; por defecto, se incluyen todos
los niveles. Más información sobre el árbol TOC en [este enlace](https://www.sphinx-doc.org/en/master/usage/restructuredtext/directives.html). En
resumen, al añadir archivos *.rst a nuestra tabla de contenido, deben aparecer aquí.
Añadamos un archivo para ver cómo funciona esto.

Crea un archivo `about.rst`, también en la carpeta raíz principal, con el contenido:

~~~
About
=====

Hello, this is the about page of my project.
~~~
>
{: .language-markdown }

Ahora vamos a añadir este archivo al árbol TOC editando el archivo `index.rst`:

~~~
.. this is a comment, it is not rendered

Sphinx Example Project's documentation
======================================

Contents:

.. toctree::
    :maxdepth: 2

    about.rst
~~~
>
{: .language-markdown }

Ya está: nuestra página de inicio (generada con el archivo `index.rst`) enlazará ahora
con la página Acerca de (`about.rst`). A continuación, vamos a escribir un archivo
`conf.py` mínimo, también en el directorio raíz.

~~~
# -- Project information -----------------------------------------------------

project = 'My project'
copyright = '2021, <Your name>'
author = '<Your name>'
release = '1.0'

# -- Options for HTML output -------------------------------------------------

html_theme = 'alabaster'
~~~
>
{: .language-bash }

Para obtener una lista completa de las opciones que se pueden especificar en este
archivo, consulte la
[documentación](https://www.sphinx-doc.org/en/master/usage/configuration.html).

> ## Inicio rápido de Sphinx
> Una vez más, tener Sphinx instalado localmente le ayudará en las siguientes etapas. De
> hecho, usted puede construir su sitio web de documentación localmente a través del
> comando `sphinx-build . build/` para ser ejecutado en su carpeta raíz. Una vez
> ejecutado, se generará el sitio web de salida en la carpeta `build/`. Puedes
> visualizarlo simplemente abriendo el archivo `index.html` a través de tu navegador
> favorito.
>
{: .callout}

También en este caso, el archivo `.gitlab-ci.yml` es necesario para especificar las
instrucciones para el despliegue de GitLab. Rellénalo con:

~~~
pages:
  stage: deploy
  image: python:3.6
  script:
    - pip install -U sphinx
    - sphinx-build -b html . public
  artifacts:
    paths:
      - public
~~~
>
{: .language-yaml }

Este script: especifica el contenedor para nuestro pipeline (Python, versión 3.6),
instala Sphinx a través de [Pip](https://pypi.org/project/pip/), ejecuta el comando
`sphinx-build` - que construye archivos HTML en la carpeta raíz (`.`) a una carpeta
`public` que también crea. Finalmente, especifica dónde encontrar los artefactos HTML
(en la carpeta `public`, efectivamente).

Ya está todo listo. Ahora debemos seguir una vez más la "Configuración de un proyecto"
en la
[introducción](https://grp-bio-it-workshops.embl-community.io/building-websites-with-gitlab/01-introduction/index.html)
para configurar un proyecto remoto en GitLab, configurarlo como remoto para nuestra
carpeta local con `git remote add origin <git URL>`, `git add . && git commit -m
<message>` y luego `git push -u`. Finalmente, monitoriza la ejecución de tu pipeline y
comprueba el resultado final.

{% include links.md %}

