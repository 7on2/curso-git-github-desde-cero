# Laboratorio: Terminal Y Archivos Para Git

## Objetivo

Practicar comandos basicos de terminal usando un proyecto pequeno. Al finalizar, el repositorio tendra una estructura clara y lista para empezar a versionarse con Git.

## Que Se Practica

- Crear carpetas y archivos.
- Moverse entre rutas.
- Ver contenido.
- Organizar un proyecto simple.
- Preparar una base de trabajo para Git.

## 1. Crear El Espacio De Trabajo

```bash
mkdir lab-terminal-git
cd lab-terminal-git
pwd
```

`pwd` confirma la ruta actual. Antes de crear o borrar archivos, conviene saber donde estas.

## 2. Crear Una Estructura De Proyecto

```bash
mkdir docs src assets
touch README.md src/app.txt docs/notas.txt
ls
```

Resultado esperado:

```text
README.md  assets  docs  src
```

Idea clave:

- `mkdir` crea carpetas.
- `touch` crea archivos vacios.
- `ls` muestra que existe en la ruta actual.

## 3. Escribir Contenido Inicial

```bash
echo "# Laboratorio Terminal Git" > README.md
echo "Aplicacion de practica" > src/app.txt
echo "Comandos usados: mkdir, cd, touch, echo, cat, ls" > docs/notas.txt
```

`>` reemplaza el contenido del archivo. Si el archivo no existe, lo crea.

## 4. Leer Archivos

```bash
cat README.md
cat src/app.txt
cat docs/notas.txt
```

`cat` permite verificar rapidamente el contenido de archivos pequenos.

## 5. Agregar Mas Contenido Sin Reemplazar

```bash
echo "Este proyecto servira para practicar Git." >> README.md
cat README.md
```

`>>` agrega contenido al final del archivo sin borrar lo anterior.

## 6. Renombrar Y Copiar

```bash
cp docs/notas.txt docs/notas-backup.txt
mv src/app.txt src/main.txt
ls docs
ls src
```

Idea clave:

- `cp` copia.
- `mv` mueve o renombra.
- Mantener nombres claros ayuda a que el historial de Git sea mas facil de leer.

## 7. Ver Estructura Final

```bash
ls -R
```

Resultado esperado:

```text
README.md
assets
docs
src

docs:
notas-backup.txt
notas.txt

src:
main.txt
```

## Verificacion Final

El laboratorio esta completo si puedes responder:

- Donde esta ubicado el proyecto?
- Que diferencia hay entre `>` y `>>`?
- Que comando muestra contenido de un archivo?
- Que comando permite renombrar un archivo?

