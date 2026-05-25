# Laboratorio: Staging Y Commits Atomicos

## Objetivo

Entender la diferencia entre working directory, staging area y commit. Al finalizar, el historial tendra commits pequenos y faciles de leer.

## Que Se Practica

- `git status`
- `git add`
- `git diff`
- `git diff --staged`
- `git commit`
- commits atomicos

## 1. Crear El Repositorio

```bash
mkdir lab-commits-atomicos
cd lab-commits-atomicos
git init -b main
```

## 2. Crear La Version Inicial

```bash
echo "# Tienda DevOps" > README.md
echo "Producto: Curso Git" > productos.txt
git status
```

Git debe mostrar archivos sin rastrear.

Prepara y confirma:

```bash
git add README.md productos.txt
git diff --staged
git commit -m "Crea catalogo inicial"
```

Idea clave:

- `git add` no guarda definitivamente.
- `git add` prepara cambios para el proximo commit.
- `git commit` crea el punto real del historial.

## 3. Hacer Dos Cambios Diferentes

```bash
echo "Producto: Curso Docker" >> productos.txt
echo "## Objetivo" >> README.md
echo "Practicar control de versiones." >> README.md
git status
git diff
```

Hay dos tipos de cambio:

- cambio en catalogo,
- cambio en documentacion.

En lugar de hacer un solo commit gigante, separamos por intencion.

## 4. Commit Atomico Del Catalogo

```bash
git add productos.txt
git diff --staged
git commit -m "Agrega producto Docker"
```

Este commit solo habla del catalogo.

## 5. Commit Atomico De Documentacion

```bash
git status
git add README.md
git diff --staged
git commit -m "Documenta objetivo del proyecto"
```

Este commit solo habla del README.

## 6. Leer El Historial

```bash
git log --oneline
```

El historial debe mostrar tres commits:

```text
Documenta objetivo del proyecto
Agrega producto Docker
Crea catalogo inicial
```

## Verificacion Final

El laboratorio esta completo si puedes explicar:

- Que muestra `git status`?
- Para que sirve `git diff` antes de un commit?
- Para que sirve `git diff --staged`?
- Por que conviene separar cambios en commits atomicos?

