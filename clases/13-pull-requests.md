# Pull Requests Y Colaboracion En GitHub

Un Pull Request, o PR, es una propuesta de cambio. No es solo un boton para fusionar ramas: es el espacio donde se revisa, conversa y aprueba trabajo antes de mezclarlo con la rama principal.

## Flujo Mental De Un PR

```mermaid
flowchart LR
    A["Crear rama"] --> B["Hacer commits"]
    B --> C["Push a GitHub"]
    C --> D["Abrir Pull Request"]
    D --> E["Revision"]
    E --> F["Merge a main"]

    style A fill:#1f6feb,stroke:#58a6ff,color:#fff
    style B fill:#238636,stroke:#3fb950,color:#fff
    style C fill:#30363d,stroke:#8b949e,color:#fff
    style D fill:#8957e5,stroke:#bc8cff,color:#fff
    style E fill:#9e6a03,stroke:#d29922,color:#fff
    style F fill:#238636,stroke:#3fb950,color:#fff
```

## Crear Una Rama Para Trabajar

```bash
git switch -c feature/contacto
```

Haces cambios, preparas y confirmas:

```bash
git add .
git commit -m "agrego formulario de contacto"
```

Subes la rama:

```bash
git push -u origin feature/contacto
```

Luego GitHub te mostrara la opcion para abrir un Pull Request.

## Que Debe Tener Un Buen Pull Request

- Titulo claro.
- Descripcion de que cambia.
- Capturas si es visual.
- Pasos para probar.
- Relacion con un issue si existe.

Ejemplo simple:

```text
Titulo: agrega formulario de contacto

Cambios:
- agrega contact.html
- conecta estilos basicos
- actualiza links del menu

Prueba:
- abrir index.html
- entrar al enlace Contacto
```

## Revisar Cambios En GitHub

En un PR puedes ver:

- Archivos modificados.
- Lineas agregadas y eliminadas.
- Conversaciones por linea.
- Checks automaticos si el proyecto tiene CI.

## Formas De Fusionar Un PR

| Metodo | Cuando usarlo |
|---|---|
| Merge commit | Mantiene la historia completa de la rama |
| Squash and merge | Junta varios commits en uno solo |
| Rebase and merge | Reescribe la historia para dejarla lineal |

Para cursos iniciales, normalmente conviene explicar primero **Merge commit**. Luego se puede mostrar **Squash** cuando ya entienden el historial.

## Issues En GitHub

Un issue sirve para registrar una tarea, error o mejora.

Ejemplos:

```text
Corregir ejemplo de git restore
Agregar laboratorio de ramas
Mejorar colores de diagramas
```

Un flujo practico seria:

```text
Issue -> Rama -> Commit -> Push -> Pull Request -> Merge
```

## Comandos Resumen

| Accion | Comando |
|---|---|
| Crear rama | `git switch -c nombre-rama` |
| Subir rama | `git push -u origin nombre-rama` |
| Ver ramas remotas | `git branch -r` |
| Actualizar datos remotos | `git fetch` |
| Volver a main | `git switch main` |
| Traer main actualizado | `git pull` |

---

[&larr; Anterior: Remotos](./12-remotos-github.md) | [Siguiente: Forks y open source &rarr;](./14-forks-open-source.md)
