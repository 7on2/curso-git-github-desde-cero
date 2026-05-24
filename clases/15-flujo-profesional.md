# Flujo Profesional Con Git Y GitHub

Este modulo junta las piezas anteriores en una forma de trabajo mas cercana a equipos reales.

## Flujo Diario Recomendado

```bash
git switch main
git pull
git switch -c feature/nueva-seccion
# trabajar archivos
git status
git diff
git add .
git commit -m "agrego nueva seccion"
git push -u origin feature/nueva-seccion
```

Luego abres un Pull Request en GitHub.

## Antes De Hacer Commit

Revisa:

```bash
git status
git diff
git diff --staged
```

Esto evita commits con archivos de mas, cambios temporales o pruebas que no querias subir.

## Mensajes De Commit Menos Roboticos

Un error comun al usar asistentes de IA es terminar con mensajes demasiado perfectos, largos o genericos.

Suena artificial:

```text
Implement comprehensive course modularization and improve diagram readability
Enhance educational content with robust pedagogical structure
```

Suena mas humano y sigue siendo util:

```text
separo clases en modulos
agrego tema de remotos
arreglo colores de mermaid
mejoro explicacion de commits
```

La regla no es escribir peor. La regla es escribir como una persona que conoce su cambio.

## Convenciones Simples De Ramas

| Tipo | Ejemplo |
|---|---|
| Nueva funcion | `feature/login` |
| Correccion | `fix/error-menu` |
| Documentacion | `docs/guia-ramas` |
| Experimento | `chore/prueba-diagramas` |

## Tags Y Releases

Un tag marca una version importante del proyecto.

```bash
git tag v1.0.0
git push origin v1.0.0
```

En GitHub, los tags pueden convertirse en **Releases**, utiles para publicar versiones descargables o hitos del curso.

## Stash, Rebase, Cherry-Pick Y Reflog

Estos comandos son utiles, pero conviene verlos despues de dominar commits, ramas, merge y remotos.

| Comando | Para que sirve |
|---|---|
| `git stash` | Guardar cambios temporalmente sin commit |
| `git rebase` | Reordenar o reaplicar commits sobre otra base |
| `git cherry-pick` | Traer un commit especifico de otra rama |
| `git reflog` | Ver movimientos recientes de HEAD para recuperar trabajo |

## GitHub Actions En Una Frase

GitHub Actions permite automatizar tareas cuando ocurre algo en el repo, por ejemplo correr pruebas cada vez que se abre un Pull Request.

Para un curso inicial basta con entender la idea:

```text
push o pull request -> GitHub ejecuta un workflow -> resultado visible en GitHub
```

## Cierre Del Curso

Al terminar este recorrido deberias poder:

- Crear y configurar repositorios.
- Hacer commits claros.
- Leer historial.
- Deshacer cambios sin destruir trabajo.
- Trabajar con ramas.
- Resolver conflictos.
- Subir cambios a GitHub.
- Abrir Pull Requests.
- Contribuir mediante forks.

---

[&larr; Anterior: Forks y open source](./14-forks-open-source.md) | [Bonus: Loki y la Linea Temporal &rarr;](./16-bonus-loki.md)
