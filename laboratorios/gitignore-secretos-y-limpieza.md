# Laboratorio: .gitignore, Secretos Y Limpieza

## Objetivo

Aprender a evitar que Git rastree archivos locales, temporales o sensibles. Al finalizar, el repositorio tendra un `.gitignore` util y un historial sin secretos.

## Que Se Practica

- Crear `.gitignore`.
- Identificar archivos que no deben subirse.
- Verificar que Git ignore archivos.
- Limpiar un archivo que fue agregado por error al staging.

## 1. Crear Repositorio

```bash
mkdir lab-gitignore
cd lab-gitignore
git init -b main
```

## 2. Crear Archivos Del Proyecto

```bash
echo "# App Configurable" > README.md
echo "console.log('app iniciada')" > app.js
echo "TOKEN=123456" > .env
echo "debug.log" > app.log
mkdir dist
echo "archivo generado" > dist/bundle.js
git status
```

Git mostrara todo como archivo nuevo. Pero no todo debe entrar al repositorio.

## 3. Crear .gitignore

```bash
echo ".env" > .gitignore
echo "*.log" >> .gitignore
echo "dist/" >> .gitignore
cat .gitignore
```

Reglas:

- `.env`: variables locales o secretos.
- `*.log`: archivos de log.
- `dist/`: archivos generados.

## 4. Verificar Estado

```bash
git status
```

Ahora Git debe mostrar principalmente:

```text
.gitignore
README.md
app.js
```

`.env`, `app.log` y `dist/` ya no deben aparecer como pendientes.

## 5. Confirmar Solo Lo Correcto

```bash
git add .gitignore README.md app.js
git commit -m "Configura archivos base e ignore"
```

## 6. Simular Un Error En Staging

Crea un archivo temporal nuevo:

```bash
echo "cache local" > cache.tmp
git add cache.tmp
git status
```

Si no querias agregarlo, sacalo del staging:

```bash
git restore --staged cache.tmp
git status
```

Luego agregalo al `.gitignore`:

```bash
echo "*.tmp" >> .gitignore
git add .gitignore
git commit -m "Ignora archivos temporales"
```

## Verificacion Final

El laboratorio esta completo si puedes explicar:

- Por que `.env` no debe entrar al repositorio?
- Que significa `*.log`?
- Que hace `git restore --staged archivo`?
- Como verificas que un archivo esta siendo ignorado?

