# Deshacer Cambios En Git

## Deshacer Modificaciones En Un Archivo

Si modificaste un archivo y quieres volver a la ultima version confirmada:

```bash
git restore archivo.txt
```

Esto descarta los cambios no preparados y restaura el archivo a su ultimo estado en el commit.

## Quitar Un Archivo Del Staging

Si preparaste un archivo por error y quieres sacarlo del area de staging:

```bash
git restore --staged archivo.txt
```

El archivo vuelve al directorio de trabajo pero conserva tus cambios.

## Ver El Estado Despues De Restaurar

```bash
git status
```

## Ejemplo Completo

```bash
# Crear y modificar un archivo
echo "nuevo contenido" >> archivo.txt

# Ver el cambio
git status

# Deshacer el cambio
git restore archivo.txt

# Verificar que volvio al estado anterior
git status
```

## Si Ya Hiciste Commit

Si el cambio ya fue confirmado con `git commit`, puedes usar `git revert`.

### Como Elegir La Forma De Deshacer

```mermaid
flowchart TD
    A["Quiero deshacer algo"] --> B{"Ya hice commit?"}
    B -->|No| C{"Esta en staging?"}
    C -->|No| D["git restore archivo.txt"]
    C -->|Si| E["git restore --staged archivo.txt"]
    E --> F["Cambios vuelven al working directory"]
    B -->|Si| G["git revert hash"]
    G --> H["Nuevo commit correctivo"]

    style A fill:#30363d,stroke:#8b949e,color:#fff
    style B fill:#8957e5,stroke:#bc8cff,color:#fff
    style C fill:#8957e5,stroke:#bc8cff,color:#fff
    style D fill:#da3633,stroke:#f85149,color:#fff
    style E fill:#9e6a03,stroke:#d29922,color:#fff
    style F fill:#1f6feb,stroke:#58a6ff,color:#fff
    style G fill:#238636,stroke:#3fb950,color:#fff
    style H fill:#1f6feb,stroke:#58a6ff,color:#fff
```

### Ver El Historial

```bash
git log --oneline
```

### Revertir Un Commit

```bash
git revert <hash-del-commit>
```

Esto crea un nuevo commit que deshace los cambios del commit especificado, sin borrar el historial.

## Resumen De Comandos

| Accion | Comando |
|---|---|
| Descartar cambios en archivo | `git restore archivo.txt` |
| Quitar del staging | `git restore --staged archivo.txt` |
| Revertir un commit | `git revert <hash>` |
| Ver estado | `git status` |

## Laboratorio Relacionado

- [Deshacer cambios con criterio](../laboratorios/deshacer-cambios-con-criterio.md): practica como corregir cambios no confirmados, cambios en staging y commits ya creados.

---

[&larr; Anterior: Estados, staging y commits](./06-estados-staging-commits.md) | [Siguiente: .gitignore y buenas practicas &rarr;](./08-gitignore.md)
