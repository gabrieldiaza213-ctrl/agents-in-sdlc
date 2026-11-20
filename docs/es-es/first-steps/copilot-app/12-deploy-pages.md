---
title: "Lección 12 - Desplegar el sitio con GitHub Pages"
description: "Usa la aplicación GitHub Copilot para configurar un flujo de trabajo de Pages, revisar su solicitud de incorporación de cambios y comprobar el Space Quiz publicado."
authors:
  - jamesmontemagno
lastUpdated: 2026-10-12
---

Publica Space Quiz en GitHub Pages para que todo el mundo pueda acceder a él. Copilot puede preparar el flujo de trabajo y guiarte durante el despliegue, pero tú debes revisar los cambios y confirmar que el sitio está disponible.

En esta lección:

- pedirás a Copilot que configure un despliegue con GitHub Pages.
- revisarás el flujo de trabajo y la solicitud de incorporación de cambios antes de combinarla.
- seguirás el despliegue y comprobarás el sitio publicado.

## Escenario

Space Quiz ya está en un repositorio de GitHub, pero hace falta una forma sencilla de probarlo. Publicar el sitio, que consta de un solo archivo, con GitHub Pages permite acceder a él desde una URL pública sin añadir un servidor ni una dependencia del entorno de ejecución.

## Pide a Copilot que prepare el despliegue

> [!WARNING]
> Crear una solicitud de incorporación de cambios puede confirmar y enviar código. Revisa la configuración de aprobaciones y el repositorio de destino antes de enviar este prompt. Si está seleccionada la opción **Approve all**, no esperes que aparezca una solicitud de confirmación independiente.

En la sesión de la aplicación Copilot para `space-quiz`, envía este prompt:

```plaintext
Prepara un despliegue de GitHub Pages para este repositorio. Crea un flujo de trabajo de GitHub Actions que compile el sitio web si es necesario y lo despliegue en GitHub Pages cuando los cambios lleguen a la rama predeterminada. Añade un README que describa la aplicación y cómo ejecutarla localmente si aún no existe. Crea una solicitud de incorporación de cambios con estos cambios e indica su enlace y cualquier configuración o permiso de Pages necesario. No combines la solicitud, no actives la combinación automática, no cambies la configuración de Pages ni despliegues el sitio. Detente y espera a que revise los cambios.
```

## Revisa el flujo de trabajo y la solicitud de incorporación de cambios

1. Confirma que el README solo se añade si el repositorio aún no tiene uno.
2. Revisa los cambios de la solicitud, incluidos los pasos de compilación y despliegue del flujo de trabajo, sus activadores y sus permisos.
3. Confirma que el flujo despliega desde la rama predeterminada, no desde una solicitud de incorporación de cambios que aún no se haya combinado.
4. Solicita las correcciones necesarias y revisa el diff actualizado. Espera a que se superen las comprobaciones obligatorias de la solicitud antes de autorizar su combinación.

## Autoriza la combinación y el despliegue

> [!WARNING]
> El siguiente prompt autoriza al agente a combinar la solicitud de incorporación de cambios revisada, cambiar la configuración de Pages del repositorio y publicar el sitio. Envíalo solo después de revisar los cambios y confirmar el repositorio y la solicitud. Según la configuración de aprobaciones, estas acciones podrían realizarse sin otra confirmación.

Sustituye `<PR_NUMBER>` por el número de la solicitud que has revisado y envía este prompt por separado:

```plaintext
He revisado la solicitud de incorporación de cambios <PR_NUMBER> en este repositorio y autorizo su combinación y el despliegue. Habilita GitHub Pages con GitHub Actions, combina esa solicitud solo después de que se superen las comprobaciones obligatorias y supervisa el despliegue hasta que finalice correctamente. Indica la URL final del sitio web publicado. Si no tienes permiso para habilitar Pages o combinar la solicitud, dime exactamente qué debo aprobar o hacer; no informes de que se ha completado hasta que el sitio esté publicado.
```

![Diagrama de tres etapas: una solicitud de incorporación de cambios de space-quiz combinada; una ejecución correcta de GitHub Actions para desplegar el sitio web, con los pasos Build website, Upload artifact y Deploy to Pages; y Space Quiz publicado en yourname.github.io/space-quiz/.](../../../_images/first-steps-app-pages-deploy.svg)

## Comprueba el despliegue

1. Sigue la ejecución del despliegue de GitHub Actions hasta que finalice correctamente.
2. Abre la URL indicada y confirma que Space Quiz se carga.

Si el agente no puede habilitar Pages o combinar la solicitud de incorporación de cambios, sigue las instrucciones concretas que te proporcione. No des la tarea por terminada hasta que el despliegue finalice correctamente y el sitio publicado se cargue.

## Resumen y siguientes pasos

Space Quiz ya está disponible como sitio web y has comprobado el despliegue en lugar de depender del informe del agente. Continúa con la [Lección 13: Revisión y siguientes pasos][next-lesson].

[next-lesson]: ../13-review/
