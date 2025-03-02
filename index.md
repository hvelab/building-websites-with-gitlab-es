---
layout: lesson
root: .
permalink: index.html
---


> ## Requisitos previos
> Antes de seguir esta lección, los alumnos deberían ser capaces de:
> 
> 1. crear un proyecto en [GitLab][gitlab] / [EMBL GitLab][embl-gitlab].
> 1. clonar una copia local de un proyecto con Git, añadir y confirmar archivos
>    modificados, y empujar/tirar cambios entre repositorios locales y remotos.
> 1. ejecutar comandos en el shell.
> 
> Ninguno de los prerrequisitos anteriores es absolutamente necesario para seguir la
> lección. Sin embargo, serán necesarios para gestionar eficientemente el desarrollo del
> sitio web desde tu portátil y probar cómo queda antes de crear versiones oficiales.
> 
> Si quieres aprender cualquiera de las habilidades listadas arriba, las lecciones de
> [Software Carpentry][swc] sobre [the Shell][swc-shell] y [Git][swc-git] son un buen
> lugar para empezar.
> 
{: .prereq }

Para aquellos que ya están familiarizados con las formas en que Git y una plataforma en
línea como GitLab o GitHub pueden ayudarles a rastrear y comparar cambios en archivos de
texto plano y colaborar con otros en proyectos, __GitLab__ (y GitHub) __Pages__
proporcionan una forma gratuita de construir y alojar páginas web. Este enfoque se
utiliza habitualmente para proporcionar documentación sobre proyectos de software, y
para crear blogs y sitios web para personas y organizaciones ya acostumbradas a trabajar
con el conjunto de herramientas Git para sus otros proyectos. Sin embargo, para aquellos
que dan sus primeros pasos en la creación de sitios de este tipo, el proceso puede
resultar confuso e intimidatorio. Este tutorial pretende resolver este problema
1. proporciona una guía paso a paso para crear una colección de páginas,
1. mostrando múltiples ejemplos de cómo estructurarlos en un sitio coherente,
1. Demostración del uso de múltiples frameworks para el desarrollo de páginas web, desde
   _HTML_ a _Jekyll_ y _Sphinx_.

También se tratará brevemente la diferencia entre el desarrollo de páginas en GitLab y
en GitHub.

> ## Capturas de pantalla obsoletas
> 
> A lo largo de esta lección haremos uso y mostraremos contenido y capturas de pantalla
> de [git.embl.de](https://git.embl.de/). Como plataforma en constante evolución, GitLab
> siempre está añadiendo nuevas características y nuevos elementos visuales a su sitio
> web. **Las capturas de pantalla** de la lección pueden desincronizarse, hacer
> referencia o mostrar contenido que ya no existe.
> 
> Si durante la lección encuentras **capturas de pantalla** que no coinciden con lo que
> ves en tu navegador, por favor [abre una
> incidencia](https://git.embl.de/grp-bio-it-workshops/building-websites-with-gitlab/-/issues)
> describiendo lo que ves y en qué difiere del contenido de la lección. No dudes en
> añadir tantas capturas de pantalla como sea necesario para aclarar la discrepancia.
> 
{: .callout }

> ## Objetivos de aprendizaje
> 
> Después de seguir esta lección, los alumnos serán capaces de:
> 
> - __crear__ contenido de página formateado con _HTML_ o _Markdown_
> - __configurar__ su proyecto para construir y servir páginas en GitLab
> - __build__ un sitio simple para alojar contenido en _HTML_ plano
> - __construir__ un sitio coherente con múltiples páginas usando el _Jekyll_ o el
>   _Sphinx_ framework
> - __personalizar__ el diseño y el estilo de las páginas de su sitio web
> 
{: .objectives }

[gitlab]: https://gitlab.com/
[embl-gitlab]: https://git.embl.de/

{% include links.md %}

