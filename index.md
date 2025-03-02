---
permalink: index.html
site: sandpaper::sandpaper_site
---

:::::::::::::::::::::::::::::::::::::::::  prereq

## Requisitos previos

Antes de seguir esta lección, los alumnos deberían ser capaces de:

1. crear un proyecto en [GitLab][gitlab] / [EMBL GitLab][embl-gitlab].
2. clonar una copia local de un proyecto con Git, añadir y confirmar archivos
  modificados, y empujar/tirar cambios entre repositorios locales y remotos.
3. ejecutar comandos en el shell.

Ninguno de los prerrequisitos anteriores es absolutamente necesario para seguir la
lección. Sin embargo, serán necesarios para gestionar eficientemente el desarrollo del
sitio web desde tu portátil y probar cómo queda antes de crear versiones oficiales.

Si quieres aprender cualquiera de las habilidades listadas arriba, las lecciones de
[Software Carpentry][swc] sobre [the Shell][swc-shell] y [Git][swc-git] son un buen
lugar para empezar.

::::::::::::::::::::::::::::::::::::::::::::::::::

Para aquellos que ya están familiarizados con las formas en que Git y una plataforma en
línea como GitLab o GitHub pueden ayudarles a rastrear y comparar cambios en archivos de
texto plano y colaborar con otros en proyectos, **GitLab** (y GitHub) **Pages**
proporcionan una forma gratuita de construir y alojar páginas web. Este enfoque se
utiliza habitualmente para proporcionar documentación sobre proyectos de software, y
para crear blogs y sitios web para personas y organizaciones ya acostumbradas a trabajar
con el conjunto de herramientas Git para sus otros proyectos. Sin embargo, para aquellos
que dan sus primeros pasos en la creación de sitios de este tipo, el proceso puede
resultar confuso e intimidatorio. Este tutorial pretende resolver este problema

1. proporciona una guía paso a paso para crear una colección de páginas,
2. mostrando múltiples ejemplos de cómo estructurarlos en un sitio coherente,
3. Demostración del uso de múltiples frameworks para el desarrollo de páginas web, desde
  *HTML* a *Jekyll* y *Sphinx*.

También se tratará brevemente la diferencia entre el desarrollo de páginas en GitLab y
en GitHub.

::::::::::::::::::::::::::::::::::::::::  callout

## Capturas de pantalla obsoletas

A lo largo de esta lección haremos uso y mostraremos contenido y capturas de pantalla
de [git.embl.de][embl-gitlab]. Como plataforma en constante evolución, GitLab
siempre está añadiendo nuevas características y nuevos elementos visuales a su sitio
web. **Las capturas de pantalla** de la lección pueden desincronizarse, hacer
referencia o mostrar contenido que ya no existe.

Si durante la lección encuentras **capturas de pantalla** que no coinciden con lo que
ves en tu navegador, por favor [abre una
incidencia](https://git.embl.de/grp-bio-it-workshops/building-websites-with-gitlab/-/issues)
describiendo lo que ves y en qué difiere del contenido de la lección. No dudes en
añadir tantas capturas de pantalla como sea necesario para aclarar la discrepancia.

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::  objectives

## Objetivos de aprendizaje

Después de seguir esta lección, los alumnos serán capaces de:

- **crear** contenido de página formateado con *HTML* o *Markdown*
- **configurar** su proyecto para construir y servir páginas en GitLab
- **build** un sitio simple para alojar contenido en *HTML* plano
- **construir** un sitio coherente con múltiples páginas usando el *Jekyll* o el
  *Sphinx* framework
- **personalizar** el diseño y el estilo de las páginas de su sitio web

::::::::::::::::::::::::::::::::::::::::::::::::::



[gitlab]: https://gitlab.com/
[embl-gitlab]: https://git.embl.de/



