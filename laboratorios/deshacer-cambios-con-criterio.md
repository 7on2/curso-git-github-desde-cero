# Laboratorio: Deshacer Cambios Con Criterio

## Objetivo

Practicar formas seguras de corregir errores segun el estado del cambio: modificado, en staging o confirmado en un commit.

## Que Se Practica

- `git restore`
- `git restore --staged`
- `git commit --amend`
- `git revert`
- lectura del historial

## 1. Crear Repositorio Base

```bash
mkdir lab-deshacer
cd lab-deshacer
git init -b main

echo "# Proyecto Seguro" > README.md
echo "version=1" > config.txt
git add .
git commit -m "Crea configuracion inicial"
```

## 2. Deshacer Un Cambio No Confirmado

Modifica un archivo:

```bash
echo "linea incorrecta" >> config.txt
git status
git diff
```

Si el cambio no sirve, descartalo:

```bash
git restore config.txt
git status
```

Idea clave:

`git restore archivo` descarta cambios que aun no fueron confirmados. Antes de usarlo, revisa con `git diff`.

## 3. Sacar Un Archivo Del Staging

```bash
echo "modo=dev" >> config.txt
git add config.txt
git status
```

El archivo esta preparado para commit. Si todavia no quieres confirmarlo:

```bash
git restore --staged config.txt
git status
```

El cambio sigue en el archivo, pero ya no esta en staging.

Ahora confirmalo correctamente:

```bash
git add config.txt
git commit -m "Agrega modo de ejecucion"
```

## 4. Corregir El Ultimo Commit

Agrega una linea:

```bash
echo "puerto=8080" >> config.txt
git add config.txt
git commit -m "Agrega puerto"
```

El mensaje es poco claro. Corrigelo:

```bash
git commit --amend -m "Configura puerto por defecto"
```

Idea clave:

`amend` reescribe el ultimo commit. Es util si el commit aun no fue compartido.

## 5. Revertir Un Commit

Crea un cambio que despues se decidira deshacer:

```bash
echo "debug=true" >> config.txt
git add config.txt
git commit -m "Activa debug permanente"
```

Ver historial:

```bash
git log --oneline
```

Revierte el ultimo commit:

```bash
git revert HEAD
```

Si Git abre editor, guarda el mensaje por defecto.

Idea clave:

`git revert` no borra historia. Crea un nuevo commit que deshace el cambio anterior.

## 6. Ver El Resultado

```bash
git log --oneline --graph --all
cat config.txt
```

## Verificacion Final

El laboratorio esta completo si puedes elegir el comando correcto:

| Situacion | Comando |
|---|---|
| Cambio no confirmado | `git restore archivo` |
| Cambio en staging | `git restore --staged archivo` |
| Corregir ultimo commit propio | `git commit --amend` |
| Deshacer un commit sin borrar historia | `git revert <hash>` |

