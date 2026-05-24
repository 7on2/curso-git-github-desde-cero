# Primer Repositorio Local

## Que Es Un Repositorio Local

Un repositorio local es una carpeta en tu maquina donde Git controla los cambios de los archivos.

- Contiene todo el historial del proyecto.
- Funciona sin necesidad de internet.
- Puedes trabajar en el de forma independiente.

## Que Hace `git init`

El comando `git init` convierte una carpeta normal en un repositorio de Git.

```bash
mkdir mi-proyecto
cd mi-proyecto
git init
```

Al ejecutar `git init`, Git crea una carpeta oculta llamada `.git` que contiene:

- El historial completo del proyecto.
- La configuracion del repositorio.
- Las referencias a ramas y commits.

**Importante**: nunca modifiques manualmente la carpeta `.git`.

## Verificar Que El Repositorio Se Creo

```bash
git status
```

Si ves un mensaje como `On branch main` o `No commits yet`, el repositorio esta listo.

## Directorio De Trabajo

El directorio de trabajo es tu carpeta normal con tus archivos. Git observa esta carpeta y detecta cambios.

```text
mi-proyecto/
├── .git/          (carpeta oculta de Git)
├── README.md      (tu archivo)
└── script.py      (tu archivo)
```

### Carpeta Visible Vs Cerebro De Git

```mermaid
flowchart TB
    Repo["mi-proyecto/"] --> Visible["Archivos visibles\nREADME.md / script.py"]
    Repo --> GitFolder[".git/\nHistorial y configuracion"]
    Visible -->|"editas aqui"| Cambios["Git detecta cambios"]
    GitFolder -->|"guarda commits"| Historial["Linea de tiempo"]

    style Repo fill:#30363d,stroke:#8b949e,color:#fff
    style Visible fill:#238636,stroke:#3fb950,color:#fff
    style GitFolder fill:#1f6feb,stroke:#58a6ff,color:#fff
    style Cambios fill:#9e6a03,stroke:#d29922,color:#fff
    style Historial fill:#8957e5,stroke:#bc8cff,color:#fff
```

## Crear Un Proyecto Desde Cero

```bash
mkdir mi-proyecto
cd mi-proyecto
git init
touch README.md
git status
```

Ahora tienes un repositorio local con un archivo sin registrar.

## Ver Archivos Ocultos

En Windows, activa "Elementos ocultos" en el explorador para ver `.git`.

En Linux/macOS:

```bash
ls -la
```

Veras la carpeta `.git` en la lista.

---

[&larr; Anterior: Instalacion y configuracion](./03-instalacion-configuracion.md) | [Siguiente: Estados, staging y commits &rarr;](./06-estados-staging-commits.md)
