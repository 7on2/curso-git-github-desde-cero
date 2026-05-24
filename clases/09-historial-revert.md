# Historial, Inspeccion Y Deshacer Con Criterio

En este punto ya no basta con saber guardar cambios. Tambien necesitamos leer el historial para entender que paso, comparar modificaciones antes de confirmar y corregir errores sin romper el trabajo de otras personas.

Esta parte cierra el recorrido principal de la guia: ya sabemos crear commits, movernos con ramas, fusionar trabajo y corregir errores comunes sin perder el control del historial.

## Leer El Historial Como Mapa

El historial no es una lista decorativa. Es la bitacora del proyecto. Si esta bien escrito, te permite reconstruir decisiones tecnicas sin tener que preguntar todo de nuevo.

Comandos utiles:

```bash
git log
git log --oneline
git log --graph --oneline --all
git show <hash>
```

```mermaid
flowchart LR
    A["git log"] --> B["Veo la lista de commits"]
    B --> C["Elijo un hash"]
    C --> D["git show hash"]
    D --> E["Entiendo que cambio y por que"]

    style A fill:#1f6feb,stroke:#58a6ff,color:#fff
    style C fill:#8957e5,stroke:#bc8cff,color:#fff
    style E fill:#238636,stroke:#3fb950,color:#fff
```

## Comparar Antes De Confirmar

Antes de hacer commit conviene revisar que estamos guardando. Muchas veces el error no esta en Git, sino en hacer commit demasiado rapido.

```bash
git diff
git diff --staged
```

- `git diff` muestra cambios que todavia no estan preparados.
- `git diff --staged` muestra lo que ya entraria al proximo commit.

## Deshacer Con Criterio

No todos los errores se corrigen igual. Primero hay que mirar donde esta el cambio:

```mermaid
flowchart TD
    A["Quiero deshacer algo"] --> B{"Ya hice commit?"}
    B -->|No| C{"Esta en staging?"}
    C -->|No| D["git restore archivo"]
    C -->|Si| E["git restore --staged archivo"]
    B -->|Si| F{"Ya comparti el historial?"}
    F -->|No| G["amend o reset con cuidado"]
    F -->|Si| H["git revert hash"]
    H --> I["Nuevo commit que corrige"]

    style D fill:#da3633,stroke:#f85149,color:#fff
    style E fill:#9e6a03,stroke:#d29922,color:#fff
    style G fill:#8957e5,stroke:#bc8cff,color:#fff
    style H fill:#238636,stroke:#3fb950,color:#fff
    style I fill:#1f6feb,stroke:#58a6ff,color:#fff
```

Comandos principales de esta parte:

```bash
git restore archivo.txt
git restore --staged archivo.txt
git commit --amend
git reset --mixed HEAD~1
git reset --hard HEAD~1
git revert <hash>
```

La regla practica es simple:

- Si aun no hiciste commit, normalmente se arregla con `restore`.
- Si el cambio esta en staging, primero lo sacas con `restore --staged`.
- Si el commit todavia es tuyo y no lo compartiste, puedes usar `amend` o `reset`.
- Si el historial ya fue compartido, `revert` suele ser la opcion mas sana porque no borra historia.

## Temas Para Ampliar Despues

Git tiene mas herramientas, pero conviene verlas cuando la base anterior ya este clara. Estos temas quedan como siguiente nivel de estudio:

```mermaid
flowchart LR
    A["Rebase"] --> B["Stash"]
    B --> C["Cherry-pick"]
    C --> D["Reflog"]
    D --> E["Hooks"]
    E --> F["Laboratorio avanzado"]

    style A fill:#8957e5,stroke:#bc8cff,color:#fff
    style B fill:#9e6a03,stroke:#d29922,color:#fff
    style C fill:#1f6feb,stroke:#58a6ff,color:#fff
    style D fill:#238636,stroke:#3fb950,color:#fff
    style E fill:#30363d,stroke:#8b949e,color:#fff
    style F fill:#da3633,stroke:#f85149,color:#fff
```

---

[&larr; Anterior: Merge y conflictos](./11-merge-conflictos.md) | [Siguiente: Bonus - Loki y la Linea Temporal &rarr;](./12-bonus-loki.md)
