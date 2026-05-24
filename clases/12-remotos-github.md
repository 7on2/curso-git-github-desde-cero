# Repositorios Remotos En GitHub

Hasta ahora el curso se ha movido principalmente en Git local. Para trabajar con GitHub necesitas conectar tu repositorio local con un repositorio remoto.

## Que Es Un Remoto

Un **remoto** es una direccion externa donde vive otra copia del repositorio. Normalmente esta copia esta en GitHub.

El remoto mas comun se llama `origin`.

```mermaid
flowchart LR
    Local["Repositorio local\ntu computadora"] -->|"git push"| Remoto["origin\nGitHub"]
    Remoto -->|"git pull"| Local
    Remoto -->|"git clone"| Otra["Otra computadora"]

    style Local fill:#1f6feb,stroke:#58a6ff,color:#fff
    style Remoto fill:#30363d,stroke:#8b949e,color:#fff
    style Otra fill:#238636,stroke:#3fb950,color:#fff
```

## Ver Remotos Configurados

```bash
git remote -v
```

Ejemplo:

```text
origin  https://github.com/usuario/proyecto.git (fetch)
origin  https://github.com/usuario/proyecto.git (push)
```

## Agregar Un Remoto

Si ya tienes un repositorio local y creaste un repo vacio en GitHub:

```bash
git remote add origin https://github.com/usuario/proyecto.git
```

Verifica:

```bash
git remote -v
```

## Subir Cambios Con `git push`

```bash
git push -u origin main
```

La primera vez se usa `-u` para decirle a Git que tu rama local `main` debe seguir a `origin/main`.

Despues puedes usar simplemente:

```bash
git push
```

## Descargar Cambios Con `git pull`

```bash
git pull
```

`git pull` trae cambios del remoto y los integra en tu rama actual.

## Clonar Un Repositorio

Si el repositorio ya existe en GitHub y quieres traerlo a tu maquina:

```bash
git clone https://github.com/usuario/proyecto.git
```

Esto crea una carpeta con:

- Los archivos del proyecto.
- El historial de Git.
- El remoto `origin` ya configurado.

## Crear Y Clonar Con GitHub CLI

Si tienes instalado `gh`, puedes trabajar con GitHub desde la terminal.

Verifica la sesion:

```bash
gh auth status
```

Crear un repositorio publico desde la carpeta actual:

```bash
gh repo create nombre-del-repo --public --source=. --remote=origin --push
```

Clonar un repositorio existente:

```bash
gh repo clone usuario/nombre-del-repo
```

Ver informacion del repositorio:

```bash
gh repo view usuario/nombre-del-repo --web
```

`gh` no reemplaza a Git. Lo complementa. Git controla versiones; `gh` conversa con GitHub.

## Flujo Basico Local A GitHub

```bash
git status
git add .
git commit -m "agrego cambios"
git push
```

## Errores Comunes

### `remote origin already exists`

Ya existe un remoto llamado `origin`.

```bash
git remote -v
git remote set-url origin https://github.com/usuario/proyecto.git
```

### `rejected because the remote contains work`

GitHub tiene cambios que tu maquina no tiene.

```bash
git pull
git push
```

### Estoy en otra rama

Revisa tu rama actual:

```bash
git branch --show-current
```

## Comandos Resumen

| Accion | Comando |
|---|---|
| Ver remotos | `git remote -v` |
| Agregar remoto | `git remote add origin URL` |
| Cambiar URL remota | `git remote set-url origin URL` |
| Subir cambios | `git push` |
| Subir primera vez | `git push -u origin main` |
| Descargar e integrar | `git pull` |
| Clonar repo | `git clone URL` |
| Crear repo con GitHub CLI | `gh repo create` |
| Clonar con GitHub CLI | `gh repo clone usuario/repo` |

---

[&larr; Anterior: Merge y conflictos](./11-merge-conflictos.md) | [Siguiente: Pull Requests &rarr;](./13-pull-requests.md)
