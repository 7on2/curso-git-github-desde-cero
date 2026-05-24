# Bonus: Loki, Git Y La Linea Temporal Sagrada

Si viste la serie **Loki** de Marvel, entender ramas de Git te resultara mucho mas facil. La serie usa un concepto llamado la **Linea Temporal Sagrada** que es practicamente una analogia perfecta de como funcionan las ramas en Git.

![La Linea Temporal Sagrada del TVA](../imagenes/sacred-timeline.png)

## La Linea Temporal Sagrada: Un Repositorio Cosmico

Imagina la Linea Temporal Sagrada como un repositorio de Git gigante, mantenido meticulosamente por la **Autoridad de Variacion Temporal (TVA)**, esos burocratas de cara seria dedicados a preservar el flujo "correcto" del tiempo. Cualquier desviacion de esta linea, conocida como **Evento Nexus**, es como un commit rebelde que podria destruir todo el multiverso.

En Git, tu rama `main` es la Linea Temporal Sagrada: es la version estable y oficial de tu proyecto.

## Loki, El Pull Request Travieso

Loki, nuestro querido Dios del Engano, es como un desarrollador travieso que sigue enviando pull requests que rompen todo. El es quien accidentalmente borro la rama master de la Linea Temporal Sagrada, causando todo tipo de caos temporal.

En Git, cuando experimentas en una rama y algo sale mal, no destruiste la rama principal. Solo borras la rama experimental y vuelves a `main`.

## Ramas De Git: Caminos Divergentes Para La Realidad

Las ramas de Git, por otro lado, divergen intencionalmente de la linea temporal principal, permitiendo a los desarrolladores experimentar sin interrumpir la estabilidad del codigo principal. Una vez que los cambios se consideran estables, pueden fusionarse de vuelta a la rama `main`.

```text
main (Linea Temporal Sagrada)
  |
  +-- feature/experimento (Rama alternativa - Loki causo un Evento Nexus)
  |
  +-- fix/correccion (Rama para arreglar un problema)
```

## Conflictos De Fusion: Dolores De Cabeza Cosmicos

En la Linea Temporal Sagrada, los Eventos Nexus surgen de desviaciones del curso predeterminado de la historia, alterando potencialmente toda la linea temporal. En Git, los **conflictos de fusion** ocurren cuando cambios en diferentes ramas intentan modificar el mismo archivo, requiriendo resolucion manual.

## Podar Ramas Y El Reset De La TVA

La costumbre de la TVA de podar ramas, o resetear lineas temporales, es como un desarrollador limpiando su repositorio de Git. Se deshacen de ramas viejas y sin usar que solo ocupan espacio y causan desorden.

En Git:

```bash
# Eliminar una rama que ya no necesitas
git branch -d nombre-rama

# Forzar eliminacion si no esta fusionada
git branch -D nombre-rama
```

## Git Reset: Un Retcon Cosmico

El comando `git reset` es basicamente un retcon cosmico, permitiendo a los desarrolladores reescribir la historia y deshacer sus errores. Pero al igual que con los viajes en el tiempo, es mejor usar este poder con moderacion, o podrias terminar creando paradojas que podrian desenredar la misma tela de la realidad.

```bash
# Cuidado: esto reescribe la historia
git reset --hard HEAD~1
```

**Advertencia**: al igual que la TVA no deberia abusar del reset, tu no deberias abusar de `git reset --hard`. Usalo solo cuando estes seguro de lo que haces.

## Dos Lineas Temporales, Un Proposito

Ya sea que estes lidiando con Lineas Temporales Sagradas o ramas de Git, el objetivo es el mismo: **mantener el orden y prevenir el caos**. La Linea Temporal Sagrada asegura que la realidad no se descarrile, mientras que las ramas de Git permiten a los desarrolladores experimentar e innovar sin romper todo.

Asi que la proxima vez que trabajes en un proyecto de Git, recuerda que no solo estas gestionando ramas de codigo; eres un **guardian cosmico**, salvaguardando la integridad de tu codigo. Y quien sabe, quizas algun dia la TVA comience a monitorear nuestros repositorios de Git, asegurandose de que no creemos Eventos Nexus que podrian destruir todo el universo del software.

> **Creditos**: Esta analogia esta basada en el articulo *"Loki, Git, and the Cosmic Retcon"* de [Gaurav Trivedi](https://beingtechnicalwriter.com/sacred-timeline-git/). Publicado en [Being Technical Writer](https://beingtechnicalwriter.com/).

---

[&larr; Anterior: Flujo profesional](./15-flujo-profesional.md) | [Volver al indice](../README.md)
