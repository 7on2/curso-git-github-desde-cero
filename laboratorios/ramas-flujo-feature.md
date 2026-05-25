# Laboratorio: Ramas Y Flujo Feature

## Objetivo

Practicar un flujo de trabajo con ramas temporales. Al finalizar, el proyecto tendra una rama integrada, una rama eliminada y un historial facil de leer.

## Que Se Practica

- `git switch -c`
- commits en ramas
- volver a `main`
- `git merge`
- eliminar ramas con `git branch -d`
- leer historial con ramas

## 1. Crear Proyecto Base

```bash
mkdir lab-ramas-feature
cd lab-ramas-feature
git init -b main

echo "<h1>Portal OTI</h1>" > index.html
echo "- Inicio" > menu.txt
git add .
git commit -m "Crea portal base"
```

`main` representa una version estable del proyecto.

## 2. Crear Rama Para Menu

```bash
git switch -c feature-menu
echo "- Cursos" >> menu.txt
echo "- Contacto" >> menu.txt
git add menu.txt
git commit -m "Agrega opciones al menu"
```

Esta rama contiene una mejora aislada.

## 3. Ver Que Main No Cambio

```bash
git switch main
cat menu.txt
```

Solo debe aparecer:

```text
- Inicio
```

Idea clave:

Cambiar de rama cambia la version del proyecto que estas viendo.

## 4. Crear Otra Mejora En Main

```bash
echo "<p>Bienvenidos al portal de cursos.</p>" >> index.html
git add index.html
git commit -m "Agrega bienvenida"
```

Ahora `main` avanzo por su lado y `feature-menu` tambien tiene su propio cambio.

## 5. Integrar La Rama Feature

```bash
git merge feature-menu
```

Como los cambios fueron en archivos distintos, Git puede integrarlos sin conflicto.

## 6. Eliminar Rama Temporal

```bash
git branch -d feature-menu
git branch
```

La rama ya fue integrada, por eso puede eliminarse de forma segura.

## 7. Ver Historial

```bash
git log --oneline --graph --all --decorate
```

## Verificacion Final

El laboratorio esta completo si puedes explicar:

- Por que se creo una rama para el menu?
- Que archivo cambio en `main`?
- Que archivo cambio en `feature-menu`?
- Por que el merge no tuvo conflicto?
- Por que `git branch -d feature-menu` fue seguro?

