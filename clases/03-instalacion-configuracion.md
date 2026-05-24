# Instalacion Y Configuracion De Git

## Verificar Si Git Esta Instalado

Antes de instalar Git, revisa si ya existe en tu equipo:

```bash
git --version
```

Si aparece una version como `git version 2.43.0`, Git ya esta instalado.

## Instalar Git

### Windows

1. Descarga el instalador desde [git-scm.com/downloads](https://git-scm.com/downloads).
2. Ejecuta el instalador.
3. Usa las opciones por defecto.
4. Abre **Git Bash** para usar comandos tipo Linux.

### macOS

```bash
brew install git
```

O descarga desde [git-scm.com/downloads](https://git-scm.com/downloads).

### Linux (Ubuntu/Debian)

```bash
sudo apt update
sudo apt install git
```

## Configurar Tu Identidad

Git necesita saber quien realiza cada commit.

```bash
git config --global user.name "Tu Nombre"
git config --global user.email "tu@email.com"
```

Esta configuracion se guarda en tu archivo `~/.gitconfig` y se aplica a todos tus repositorios.

## Configurar El Editor Por Defecto

Puedes elegir que editor de texto usara Git para mensajes de commit:

```bash
git config --global core.editor "nano"
```

Opciones comunes:

| Editor | Comando |
|---|---|
| Nano | `git config --global core.editor "nano"` |
| VS Code | `git config --global core.editor "code --wait"` |
| Vim | `git config --global core.editor "vim"` |

## Ver La Configuracion Actual

```bash
git config --list
```

Para consultar un valor especifico:

```bash
git config user.name
git config user.email
```

## Verificar Instalacion

```bash
git --version
git config user.name
git config user.email
```

Si todos los comandos responden correctamente, Git esta listo para usar.

---

[&larr; Anterior: Terminal y Linux](./02-terminal-linux.md) | [Siguiente: Primer repositorio local &rarr;](./05-repositorio-local.md)
