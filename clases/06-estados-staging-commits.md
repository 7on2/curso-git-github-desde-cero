# Estados, Staging Y Commits

## Los Tres Estados De Git

Git trabaja con tres estados principales:

| Estado | Significado |
|---|---|
| Modificado (Working Directory) | El archivo cambio en tu carpeta de trabajo |
| Preparado (Staging Area) | El archivo esta listo para entrar al proximo commit |
| Confirmado (Repository) | El cambio ya fue guardado en el historial |

```mermaid
flowchart LR
    WD["Working Directory\nDirectorio de Trabajo"] -->|"git add"| SA["Staging Area\nArea de Preparacion"]
    SA -->|"git commit"| LR2["Local Repository\nRepositorio Local"]

    style WD fill:#da3633,stroke:#f85149,color:#fff
    style SA fill:#238636,stroke:#3fb950,color:#fff
    style LR2 fill:#1f6feb,stroke:#58a6ff,color:#fff
```

**Como funciona el flujo**:

1. **Working Directory** (rojo): Creas o modificas archivos aqui. Git detecta los cambios pero no los guarda aun.
2. **Staging Area** (verde): Usas `git add` para preparar los cambios que quieres incluir en el proximo commit.
3. **Local Repository** (azul): Usas `git commit` para guardar permanentemente los cambios preparados en el historial.

**Analogia**:

- **Working Directory**: tu taller donde trabajas en los archivos.
- **Staging Area**: la bandeja donde pones lo que quieres enviar.
- **Repository**: la caja fuerte donde se guarda todo de forma permanente.

## Revisar El Estado Del Proyecto

```bash
git status
```

Este comando muestra:

- Archivos modificados (en rojo).
- Archivos preparados (en verde).
- Rama actual.
- Si hay cambios sin preparar.

**Usalo constantemente** antes y despues de cada accion.

## Preparar Cambios

Para mover archivos del directorio de trabajo al area de staging:

```bash
git add archivo.txt
```

Para preparar todos los cambios a la vez:

```bash
git add .
```

Para preparar archivos de un tipo especifico:

```bash
git add *.md
```

## Verificar Antes De Confirmar

```bash
git status
```

Los archivos en verde estan listos para el commit.

## Crear Un Commit

```bash
git commit -m "Agrega README inicial"
```

## Que Es Un Commit

Un **commit** es una version guardada del proyecto. No guarda solamente "un archivo", sino una fotografia del estado preparado en el staging area.

Cuando haces commit, Git registra:

- Los cambios preparados con `git add`.
- El autor del cambio.
- La fecha y hora.
- Un mensaje que explica que paso.
- Un identificador unico llamado hash.
- Una referencia al commit anterior.

Visualmente, puedes pensar en un commit asi:

```mermaid
flowchart TB
    C["Commit\n9f3a21c"]
    C --> A["Autor\nTu Nombre"]
    C --> F["Fecha\n2026-05-23"]
    C --> M["Mensaje\nAgrega README inicial"]
    C --> P["Padre\ncommit anterior"]
    C --> S["Snapshot\nestado del proyecto"]

    style C fill:#1f6feb,stroke:#58a6ff,color:#fff
    style A fill:#30363d,stroke:#8b949e,color:#fff
    style F fill:#30363d,stroke:#8b949e,color:#fff
    style M fill:#238636,stroke:#3fb950,color:#fff
    style P fill:#8957e5,stroke:#bc8cff,color:#fff
    style S fill:#9e6a03,stroke:#d29922,color:#fff
```

Un commit no es una carpeta duplicada. Git guarda objetos internos y referencias para reconstruir cada version cuando sea necesario.

## Que Guarda Realmente Un Commit

- **Snapshot**: el estado confirmado de los archivos preparados.
- **Hash**: identificador unico del commit, por ejemplo `9f3a21c`.
- **Autor**: quien hizo el cambio.
- **Mensaje**: explicacion corta del cambio.
- **Padre**: el commit anterior desde donde nace este cambio.

Ejemplo de historial simple:

```text
9f3a21c Agrega README inicial
7b812aa Configura gitignore
2ac441e Corrige instrucciones de instalacion
```

Cada linea representa un punto al que puedes volver, comparar o usar como referencia.

## Commit Vs Guardar Archivo

Guardar un archivo y hacer commit no son lo mismo.

| Accion | Que significa |
|---|---|
| Guardar archivo | El cambio queda en tu carpeta local |
| `git add` | Preparas el cambio para el proximo commit |
| `git commit` | Guardas una version oficial en el historial |

Por eso puedes guardar muchas veces un archivo, pero hacer un solo commit cuando el cambio ya tiene sentido.

### Commits Y HEAD

```mermaid
flowchart LR
    A["Commit A\nInicio"] --> B["Commit B\nREADME"]
    B --> C["Commit C\nLogin"]
    C --> D["Commit D\nCorreccion"]
    HEAD["HEAD\nposicion actual"] --> D

    style A fill:#1f6feb,stroke:#58a6ff,color:#fff
    style B fill:#1f6feb,stroke:#58a6ff,color:#fff
    style C fill:#1f6feb,stroke:#58a6ff,color:#fff
    style D fill:#238636,stroke:#3fb950,color:#fff
    style HEAD fill:#da3633,stroke:#f85149,color:#fff
```

`HEAD` es un puntero que indica en que commit estas parado. Siempre apunta al ultimo commit de la rama actual.

## Ver El Historial

```bash
git log
```

Para ver una version compacta:

```bash
git log --oneline
```

## Commits Atomicos

Cada commit debe representar un solo cambio logico:

- **Bien**: `Agrega validacion de email`
- **Mal**: `cambios varios`

Un commit atomico facilita:

- Revertir cambios especificos.
- Entender el historial.
- Trabajar en equipo.

## Buenos Mensajes De Commit

- Usa imperativo: `Agrega`, `Corrige`, `Elimina`.
- Se conciso pero claro.
- Explica el que y el por que si necesario.
- Evita sonar demasiado perfecto si el repositorio es personal o de aprendizaje.

Ejemplos:

```text
Agrega pagina de login
Corrige error de validacion en formulario
Elimina archivos temporales del repositorio
```

En un curso o repo personal tambien esta bien usar mensajes mas naturales:

```text
ordeno las clases
arreglo el ejemplo del merge
agrego notas de commits
```

Lo importante es que el mensaje ayude a entender el historial. No tiene que parecer escrito por documentacion corporativa.

---

[&larr; Anterior: Primer repositorio local](./05-repositorio-local.md) | [Siguiente: Deshacer cambios &rarr;](./07-deshacer-cambios.md)
