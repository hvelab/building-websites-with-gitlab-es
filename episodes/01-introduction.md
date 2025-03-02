---
title: Introducción
teaching: 0
exercises: 0
questions:
- What is static web content?
- Why should I use GitHub or GitLab Pages to create my website?
objectives:
- Explain what a static site generator does.
- Choose the appropriate tool for your website/project.
keypoints:
- A static site generator combines page-specific content with layout elements and
  styling information to construct individual webpages.
- GitHub/GitLab Pages is a good choice for people who are already familiar with Git
  and GitHub/GitLab.
- This approach can be used to create a relatively small website/blog on a limited
  budget.
---


## Cómo funcionan los sitios web

Cuando utilizamos un navegador web para visitar una página de la World-Wide Web, el
navegador solicita información a un servidor - un ordenador que almacena los datos
relevantes para el sitio y está configurado para recibir y responder a las peticiones de
esos datos. Suponiendo que no haya problemas en esta etapa (por ejemplo, que se pida una
página que no existe o que no se pueda llegar al servidor), nuestro navegador recibe e
interpreta esta información para renderizar y mostrar la página web en nuestra pantalla.

Un desarrollador web probablemente se horrorizaría al leer una simplificación tan burda,
que es sólo una de las razones por las que los desarrolladores web no son el público
objetivo de este tutorial.

La página que muestra el navegador web es el resultado de combinar **HTML** -un formato
jerárquico que describe los elementos estructurales de la página y su contenido en
bruto- con **CSS** -un conjunto ordenado de instrucciones de estilo que indican al
navegador cómo debe organizarse y formatearse el contenido- y cualquier **imagen** que
deba incrustarse en la página. Otra información recibida del servidor, pero no mostrada
por el navegador, incluye **metadatos**, **cookies** y otros elementos no visibles en el
HTML -información sobre el sitio que podría ser relevante para un ordenador pero que
probablemente no sea interesante para un ser humano (hay
[excepciones][qwantz-easter-egg-ext] a esto)- y scripts que el navegador puede ejecutar
para hacer algo en respuesta a varios disparadores.

## Hola Mundo en HTML

Al aprender un nuevo lenguaje de programación, es frecuente encontrar una referencia al
popular ejemplo `Hello world`. Estos ejemplos suelen capturar el código más simple que
puede producir y mostrar el texto "¡Hola, mundo!" en pantalla.

Como HTML requiere que ciertas etiquetas estén presentes y casi siempre en pares
coincidentes (abrir `<tag>` y cerrar `</tag>`), los documentos HTML tienden a volverse
verbosos con bastante rapidez.

El HTML más simple y válido `Hello world` es:

~~~
<!DOCTYPE html>
<html>
  <head>
    <title>Page title</title>
  </head>
  <body>
    <p>Hello, World!</p>
  </body>
</html>
~~~
>
{: .language-html }

Así que, como puedes imaginar, escribir documentos HTML largos a mano es bastante
doloroso. Observe que no hemos especificado nada sobre cómo y dónde debe mostrarse el
texto.

Para conseguir esto necesitaríamos además incluir etiquetas estilizadas o instrucciones
Cascading Style Sheets (CSS). Si no proporciona instrucciones CSS (ya sea dentro de su
documento HTML o como un archivo separado), un navegador web hará una mejor suposición
con respecto a la disposición de los elementos HTML en la página basándose en sus
valores predeterminados.

> ## Las Muchas Etiquetas en HTML
>
> En el ejemplo `Hello world` de arriba se usan 5 etiquetas diferentes (`html`, `head`,
> `title`, `body` y `p`) en su forma abierta `<>` y cerrada `</>`. También vemos la
> etiqueta especial `doctype` que indica el formato y la versión del documento, en este
> caso, [HTML(5)][html5-wikipedia].
>
> Existen muchas otras etiquetas para definir:
> - *elementos estructurales*, como `table`, `div`, `span`, `nav`, `section`;
> - *listas*, como `ul` (para listas desordenadas) y `or` (para listas ordenadas);
> - *elementos estilizados*, como `i`/`em` (para *cursivas/énfasis*), `b`/`strong` (para
>   **negrita**) y `u` (para <u>texto subrayado</u>);
> - *encabezados*, numerados de `h1` a `h6` para títulos y subtítulos progresivamente
>   más pequeños;
> - *elementos multimedia*, como `img`, `video`, `audio` para incrustar contenido
>   multimedia enriquecido; y
> - *links*, utilizando la importante etiqueta `a` (anchor) para enlazar a secciones de
>   la misma página o a otras páginas dentro del mismo sitio web o de sitios web
>   externos.
>
> La [lista de etiquetas HTML válidas][html5-tags] es bastante extensa, cubriendo una
> rica gama de características que potencian la actual world wide web.
>
{: .callout }

> ## Ejercicio: Escribiendo HTML Básico
>
> Dado el texto estilizado:
>
> <h1><em>Hello</em>, World!</h1>
>
> escribir el HTML que producirá el mismo resultado. **Pista** la fuente grande se
> consigue mediante el uso de un encabezado.
>
> > ## Solución
> >
> > ~~~
> > <h1><em>Hello</em>, World!</h1>
> > ~~~
> > {: .language-html }
> >
> {: .solution }
>
{: .challenge }

Escribamos un ejemplo HTML más complejo utilizando una tabla que muestre el texto
"¡Hola, mundo!" en diferentes idiomas y que se renderice como: ![Ejemplo de tabla HTML](../fig/html-table.png){: .image-with-shadow width="600px" }

El HTML para producir dicha tabla tiene este aspecto (puedes copiar+pegar el fragmento
en el archivo HTML que creaste en el ejemplo anterior):
~~~
<table>
    <tr><th>Language</th><th>Text</th></tr>
    <tr><td>English</td><td>Hello, World!</td></tr>
    <tr><td>French</td><td>Bonjour, le monde!</td></tr>
    <tr><td>Portuguese</td><td>Olá, Mundo!</td></tr>
    <tr><td>Serbian</td><td>Zdravo, svete!</td></tr>
</table>
~~~
>
{: .language-html }

Cada fila está encerrada entre etiquetas **t**able **r**ow `<tr>` y `</tr>`. Dentro de
una fila, las etiquetas `<th>` y `</th>` se utilizan para contener **t**ables
**h**eadings (celdas especiales de la tabla que aparecen en negrita), mientras que las
celdas de **t**ables de **d**atos normales están contenidas dentro de las etiquetas `<td>` y
`</td>`.

Un ejemplo similar escrito utilizando listas HTML tendría el siguiente aspecto:
![Ejemplo de lista HTML](../fig/html-list.png){: .image-with-shadow width="600px" }

~~~
<ul>
    <li>English: Hello, World!</li>
    <li>French: Bonjour, le monde!</li>
    <li>Portuguese: Olá, Mundo!</li>
    <li>Serbian: Zdravo, svete!</li>
</ul>
~~~
>
{: .language-html }

Aquí, usamos etiquetas **u**nordered **l**ist `<ul>` y `</ul>` para definir una lista
con 4 elementos, cada uno a su vez envuelto en etiquetas individuales **l**ist **i**tem
(`<li>` y `</li>`).

## Sitios estáticos vs dinámicos

Las páginas _estáticas_ son aquellas cuyo contenido se almacena en un servidor en un
estado listo para ser enviado a cualquier usuario que haga una petición para esa página
web. Cuando se realiza una petición, el servidor sólo tiene que enviar la información
que compone esa página web (como HTML y CSS). Los sitios que no cambian a menudo, como
un sitio web que contiene el currículum de una persona, suelen almacenarse como sitios
estáticos.

Por el contrario, los sitios _dinámicos_ son aquellos cuyas páginas se generan cuando un
usuario solicita una página web. Dependiendo del momento en que se realice la solicitud,
el contenido puede cambiar; por ejemplo, si se hace clic en actualizar al ver un debate
en un foro web, pueden aparecer nuevos comentarios. La diferencia clave es que las
páginas estáticas sólo necesitan generarse una vez, tras lo cual permanecen sin cambios
en el servidor, en comparación con las páginas dinámicas, que son regeneradas por un
servidor cada vez que recibe una petición.

> ## Ejemplos en el ámbito de las Ciencias de la Vida
>
> Un ejemplo típico de _sitio web estático_ en el campo de las Ciencias de la Vida sería
> la documentación de una herramienta o un formato de archivo, como esta página en
> [wwpdb.org](https://www.wwpdb.org/documentation/file-format).
>
> Las páginas de entrada de la [base de datos PDB](https://www.rcsb.org/), en cambio,
> cargan el contenido de forma diferente en función de las herramientas de visualización
> y las opciones elegidas por el usuario. Una base de datos o un servidor web suele ser
> un sitio web _dinámico_.
>
{: .callout}

Esta lección se centra en los sitios estáticos y en las herramientas que se pueden
utilizar para crearlos, conocidas como **Generadores de sitios estáticos**.

Una de las ventajas de utilizar generadores de sitios estáticos es que eliminan la
necesidad de producir manualmente una gran cantidad de HTML, lo que nos permite
centrarnos en el contenido legible por humanos que queremos que contengan nuestras
páginas. Sin embargo, aún necesitamos una forma de decirle al generador cómo queremos
que se vea nuestro contenido cuando se muestre en el navegador. Para ello, utilizaremos
una herramienta llamada Markdown, sobre la que aprenderemos en un siguiente episodio.

![Las páginas pueden crearse de varias maneras: generación estática del lado del
servidor (donde el HTML se genera una vez en el servidor y no cambia a partir de
entonces), generación dinámica del lado del servidor (donde el servidor puede actualizar
y enviar nuevo HTML basándose en las peticiones del navegador del usuario), y generación
del lado del cliente (donde partes de las páginas HTML son generadas por el navegador
usando código Javascript)](../fig/page-generation-js4ds.svg)

_Figura 1.1: Alternativas de generación de páginas. Esta figura es una versión
modificada de la original publicada en [JavaScript for Data Science][js4ds], y se
reproduce aquí con permiso del autor._

Los sitios generados estáticamente son una buena opción cuando la información que se
quiere mostrar en un sitio web es la misma independientemente de quién lo visite y
cuándo, y si es poco probable que el contenido de las páginas tenga que cambiar muy a
menudo. Esto hace que los generadores de sitios estáticos sean una buena opción para
sitios que ofrecen documentación o contenido didáctico, como esta página: el objetivo de
la página es ofrecer la misma información a todos los visitantes. El visitante puede
llegar, (con suerte) encontrar y leer lo que necesita, y marcharse sintiéndose feliz y
satisfecho.

Los sitios dinámicos ofrecen muchas más posibilidades de interactividad y contenidos
personalizados o de actualidad. Pero su creación es mucho más complicada y supone una
carga adicional considerable para el servidor, sobre todo en términos de requisitos
informáticos y consideraciones de seguridad. Entre otras cosas, esto significa que, a
diferencia de lo que ocurre con las páginas estáticas (véase el resto de esta lección),
es poco probable que encuentre plataformas gratuitas que le ayuden a ofrecer contenidos
dinámicos.

> ## Ejercicio: La herramienta perfecta para el trabajo
>
> Dados los siguientes tipos de sitios web, razona si un generador de sitios estáticos
> es una solución adecuada para implementarlos.
>
> - (1) Un sitio web personal con las secciones *Acerca de* y *Proyectos
> - (2) Un foro o plataforma de debate
> - (3) Un blog comunitario o sitio web de noticias
> - (4) Un motor de búsqueda (como google.com)
> - (5) Un wiki (como wikipedia.com)
> - (6) Un libro en línea
>
> > ## Solución
> >
> > - (1) **sitio web personal**: En la mayoría de los casos, **Sí**. Este tipo de
> >   contenido suele ser escrito/editado por una sola persona y destinado a tener un
> >   acceso de sólo lectura para los visitantes.
> > - (2) **foro o discusión**: Lo más probable es que **No**. Un sitio web de este tipo
> >   requiere interactividad y formas de identificar quién escribió qué contenido.
> >
> > Para las preguntas 3 y 5 la respuesta es tanto **Sí** como **No** dependiendo de los
> > requisitos y la funcionalidad necesaria.
> >
> > - (3) **blog/noticias**: Un blog sencillo o un sitio web de noticias, mantenido por
> >   un pequeño grupo de usuarios, es perfectamente realizable utilizando un generador
> >   estático. Para grupos muy numerosos de creadores de contenidos o si es necesario
> >   controlar individualmente el acceso a los artículos, el uso de un generador
> >   estático planteará difíciles problemas técnicos.
> > - (4) **motor de búsqueda**: La mayoría de las veces **No**. Implementar algo tan
> >   sofisticado como la búsqueda de Google sería casi imposible con un generador
> >   estático. Hay formas de tener un motor simple que busque en todas las páginas
> >   producidas por un generador estático utilizando la indexación y haciendo un uso
> >   inteligente de las características del navegador, pero este enfoque tiene muchas
> >   limitaciones.
> > - (5) **wiki**: Un wiki sencillo es perfectamente factible con un generador estático
> >   (por ejemplo, [GitHub Wiki Pages](https://guides.github.com/features/wikis/)), sin
> >   embargo se vuelve limitante en cuanto su contenido necesita ser editado o
> >   discutido por muchos usuarios, como es el caso de Wikipedia.
> > - (6) **libro en línea**: Definitivamente **Sí**. Los generadores estáticos son
> >   perfectos para este tipo de sitios web. Normalmente proporcionan formas de evitar
> >   la repetición de contenido (variables y plantillas), creación automática de una
> >   *Table Of Contents*, entre otras bondades.
> >
> {: .solution }
>
{: .challenge }

## Páginas de GitLab

Si el sitio que quieres crear se ajusta bien a los puntos fuertes de un generador de
sitios estáticos -es relativamente __pequeño__, se __actualizará con poca frecuencia__,
y el __contenido no necesita ser personalizado para el visitante__ - entonces crearlo
con GitLab Pages es una buena opción. GitLab Pages es un sistema que permite a los
usuarios crear y servir sitios web directamente desde sus repositorios de GitLab. El
servicio es gratuito para los repositorios públicos y se pueden crear y servir páginas
sencillas con muy poca configuración.

Pasaremos por una lista de plantillas, de complejidad creciente. Mientras que las
primeras se basarán en Markdown plano, las más avanzadas se basarán en múltiples
tecnologías (en el diagrama siguiente se muestra un ejemplo). Puede parecer abrumador al
principio, pero explicaremos la mayoría de estas tecnologías en esta lección - sólo no
cubriremos CSS/Sass (lenguaje de estilo que se compila en CSS) y JavaScript/CoffeeScript
(lenguaje de scripting que se compila en JavaScript) en detalle.

![Static websites in GitHub Pages technology overview diagram](../fig/jekyll-gh-pages-website-overview.svg){: width="700px" }

En primer lugar, vamos a configurar un proyecto para almacenar nuestros archivos y
aprender más acerca de cómo crear y dar formato al contenido de nuestras páginas
utilizando HTML y Markdown, antes de configurar GitLab para mostrar este contenido como
un sitio web utilizando GitLab Pages.

## Configurar un proyecto

Antes de ponernos manos a la obra debemos crear un proyecto en el que trabajar. Este
proyecto es similar a una carpeta en su ordenador, las principales diferencias son que
la carpeta vive en la web en GitLab / GitHub (aunque también puede mantener una copia en
su ordenador si es necesario) y que la carpeta está utilizando un software de control de
versiones llamado [`git`](https://git-scm.com/) para realizar un seguimiento de los
cambios en los archivos. Para nuestros propósitos vamos a ignorar el software de control
de versiones, aunque puede ser útil si necesitas volver a versiones antiguas (ver
[Software Carpentry - Version Control with Git](https://swcarpentry.github.io/git-novice/) para una introducción). En esta lección
vamos a trabajar con esta carpeta en la web para controlar el sitio web que vamos a
crear.

> ## Accede a tu cuenta de GitLab
> Antes de que pueda crear un repositorio, tendrá que iniciar sesión en el
> [EMBL GitLab](https://git.embl.de/)
{: .callout}

Hay dos formas de crear un nuevo proyecto:

Haz clic en el botón "+" de la barra de navegación de la parte superior y elige "nuevo
proyecto"

![Plus button](../fig/gitlab-new-navbar.png){: .image-with-shadow width="600px" }

**o**, si estás en la página de proyectos, haz clic en el botón "Nuevo proyecto

![Botón de nuevo proyecto](../fig/gitlab-new-project.png){: .image-with-shadow
width="600px" }

Se le redirigirá a una página que ofrece tres opciones:
1. Crear proyecto en blanco
1. Crear a partir de plantilla
1. Importar proyecto Tómese su tiempo para leer las descripciones de los diferentes
   casos. Seleccione "Crear proyecto en blanco".

A continuación tendrás que rellenar algunos datos sobre tu proyecto.

![Blank new repository page](../fig/gitlab_blank_new_repo.png){: .image-with-shadow
width="600px" }

En esta lección, vamos a trabajar en un sitio web de grupo en general. Puedes imaginar
que este sitio web puede ser para tu grupo de laboratorio, un grupo de proyecto
específico u otro grupo con el que trabajes. En el campo "Nombre del proyecto", escribe
`group-website`.

El `Project slug` determinará la URL para acceder a tu proyecto y sitio web, se genera
automáticamente cuando rellenas el campo `Project name`. Déjalo como está.

Eche un vistazo al menú desplegable situado junto al campo `Project URL`. La opción por
defecto es su propio usuario, esto se refiere a su propio espacio de nombres. Otros
espacios de nombres pueden estar disponibles, dependiendo de los grupos a los que
pertenezcas. Por ejemplo, si se planea que este sea el sitio web de su grupo, puede ser
una buena opción seleccionar el espacio de nombres de su grupo para alojarlo. Esto tanto
para facilitar el acceso al proyecto a otros miembros del grupo como para tener tu
nombre de grupo (y no tu nombre de usuario) en la URL del sitio web. Sin embargo, vamos
a inicializar este proyecto de prueba en nuestro propio espacio de nombres.

También podemos añadir una descripción (por ejemplo, "Proyecto para aprender a hacer
sitios web con GitLab pages") para que sepamos qué es este proyecto cuando lo volvamos a
encontrar después del taller.

También comprobaremos la opción `Initialize repository with a README`. Es una buena
práctica tener un archivo README que da más información acerca de su repositorio.

> ## GitLab vs GitHub
>
> La mayoría de los pasos aquí descritos son muy similares en GitHub. Lo que GitLab
> llama "Proyecto", en GitHub es un "Repositorio", así que si tu instructor confunde los
> dos términos aquí está el porqué. Además, los "Grupos" son en GitLab "organizaciones".
>
> Más relevantes son las diferencias en cuanto al nivel de visibilidad y las opciones de
> configuración. En GitHub, sólo hay dos opciones disponibles para un repositorio:
> "Público" o "Privado". GitLab del EMBL permite un ajuste más específico de los
> permisos a través de la opción "Interno", es decir, accesible sólo por el usuario
> conectado. Por último, mientras que GitLab sólo permite inicializar el repositorio con
> un README, GitHub incluye la opción de inicializarlo también con un .gitignore y
> archivos de licencia.
>
{: .callout}

Una vez que hayas terminado estos pasos puedes hacer clic en el botón `Create Project`.
GitLab configurará el repositorio y debería crear el repositorio llamado `group-website`
con un archivo `README.md` en él. Lo que la interfaz gráfica nos acaba de ayudar a
hacer, son básicamente los siguientes pasos:

~~~
mkdir group-website
cd group-website
git init
cat > README.md
git add README.md
git commit -m "Initial commit"
~~~
>
{: .language-bash }

En un servidor remoto. La rama por defecto es `main`.

![Repositorio de Github para el sitio web del grupo](../fig/gitlab_group_website_project.png){: .image-with-shadow width="800px" }

Antes de pasar al siguiente capítulo, echa un vistazo a los botones de la parte
superior, como `Add LICENSE`, `Add CHANGELOG` etc., que te sugieren posibles pasos a
seguir. Por nombrar uno, la Licencia es definitivamente algo que podrías querer incluir
en tu proyecto. No vamos a examinar esto en detalle, pero tenga en cuenta que la
licencia es una buena práctica (si no necesaria) para cualquier proyecto que incluya
datos o software. Tu sitio web, aunque sea muy sencillo y estático, incluirá algún tipo
de *datos*, aunque sólo sean nombres de personas. Las tecnologías y plantillas que
utilizarás para generarlo son *software*. Un consejo.

[qwantz-easter-egg-ext]: https://chrome.google.com/webstore/detail/dinosaur-comics-easter-eg/bojkkeeefjmeogpgnlomodfkkfkfhabj
[js4ds]: http://js4ds.org
[html5-tags]: https://www.w3schools.com/TAGS/default.asp

{% include links.md %}

