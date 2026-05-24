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

Un commit es una foto del proyecto en un momento dado.

- Guarda el estado de todos los archivos preparados.
- Incluye autor, fecha y mensaje.
- Genera un identificador unico (hash SHA-1).

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
- Explica el que y el por que si es necesario.

Ejemplos:

```text
Agrega pagina de login
Corrige error de validacion en formulario
Elimina archivos temporales del repositorio
```

---

[&larr; Anterior: Primer repositorio local](./05-repositorio-local.md) | [Siguiente: Deshacer cambios &rarr;](./07-deshacer-cambios.md)