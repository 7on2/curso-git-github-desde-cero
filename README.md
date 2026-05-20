# Git y GitHub Desde Cero

![Git](https://img.shields.io/badge/Git-Fundamentos-orange)
![GitHub](https://img.shields.io/badge/GitHub-Desde%20Cero-black)
![Nivel](https://img.shields.io/badge/Nivel-Inicial-brightgreen)
![Estado](https://img.shields.io/badge/Estado-En%20Progreso-blue)

Aprende Git y GitHub desde fundamentos hasta flujos colaborativos reales, con explicaciones simples, comandos practicos y laboratorios para practicar desde casa.

## Tabla De Contenidos

- [Fundamentos Del Control De Versiones](#fundamentos-del-control-de-versiones)
  - [Que Problema Resuelve](#que-problema-resuelve)
  - [Ideas Clave](#ideas-clave)
  - [Conceptos Importantes](#conceptos-importantes)
  - [Evolucion De Los Sistemas De Versiones](#evolucion-de-los-sistemas-de-versiones)
  - [Por Que Git](#por-que-git)
- [Git, GitHub Y Ramas](#git-github-y-ramas)
  - [Que Es Git](#que-es-git)
  - [Que Es GitHub](#que-es-github)
  - [Diferencia Entre Git Y GitHub](#diferencia-entre-git-y-github)
  - [Relacion Entre Git Y GitHub](#relacion-entre-git-y-github)
  - [Que Es Una Rama](#que-es-una-rama)
  - [Main Vs Master](#main-vs-master)
  - [Loki, Git Y La Linea Temporal Sagrada](#loki-git-y-la-linea-temporal-sagrada)
- [Terminal Y Linux Basico](#terminal-y-linux-basico)
  - [Por Que Usar La Terminal](#por-que-usar-la-terminal)
  - [Comandos Basicos](#comandos-basicos)
  - [Ejemplo De Uso](#ejemplo-de-uso)
  - [Recursos Para Practicar](#recursos-para-practicar)
- [Instalacion Y Configuracion De Git](#instalacion-y-configuracion-de-git)
  - [Verificar Si Git Esta Instalado](#verificar-si-git-esta-instalado)
  - [Instalar Git](#instalar-git)
  - [Configurar Tu Identidad](#configurar-tu-identidad)
  - [Configurar El Editor Por Defecto](#configurar-el-editor-por-defecto)
  - [Ver La Configuracion Actual](#ver-la-configuracion-actual)
- [Primer Repositorio Local](#primer-repositorio-local)
  - [Que Es Un Repositorio Local](#que-es-un-repositorio-local)
  - [Que Hace `git init`](#que-hace-git-init)
  - [Verificar Que El Repositorio Se Creo](#verificar-que-el-repositorio-se-creo)
  - [Directorio De Trabajo](#directorio-de-trabajo)
  - [Crear Un Proyecto Desde Cero](#crear-un-proyecto-desde-cero)
- [Estados, Staging Y Commits](#estados-staging-y-commits)
  - [Los Tres Estados De Git](#los-tres-estados-de-git)
  - [Revisar El Estado Del Proyecto](#revisar-el-estado-del-proyecto)
  - [Preparar Cambios](#preparar-cambios)
  - [Crear Un Commit](#crear-un-commit)
  - [Ver El Historial](#ver-el-historial)
  - [Commits Atomicos](#commits-atomicos)
  - [Buenos Mensajes De Commit](#buenos-mensajes-de-commit)
- [Deshacer Cambios En Git](#deshacer-cambios-en-git)
  - [Deshacer Modificaciones En Un Archivo](#deshacer-modificaciones-en-un-archivo)
  - [Quitar Un Archivo Del Staging](#quitar-un-archivo-del-staging)
  - [Si Ya Hiciste Commit](#si-ya-hiciste-commit)
  - [Resumen De Comandos](#resumen-de-comandos)
- [Gitignore Y Buenas Practicas](#gitignore-y-buenas-practicas)
  - [Que Es `.gitignore`](#que-es-gitignore)
  - [Que Archivos Ignorar](#que-archivos-ignorar)
  - [Ejemplos Comunes](#ejemplos-comunes)
  - [Crear Un `.gitignore`](#crear-un-gitignore)
  - [`.gitignore` Global](#gitignore-global)
  - [Buenas Practicas](#buenas-practicas)
- [Laboratorio: Primer Flujo Local Con Git](#laboratorio-primer-flujo-local-con-git)
  - [Objetivo](#objetivo)
  - [Requisitos](#requisitos)
  - [Pasos](#pasos)
  - [Resultado Esperado](#resultado-esperado)
- [Material Complementario](#material-complementario)

---

## Fundamentos Del Control De Versiones

### Que Problema Resuelve

Antes de existir los sistemas de control de versiones, era comun trabajar con archivos como:

```text
proyecto.zip
proyecto_final.zip
proyecto_final_2.zip
proyecto_ahora_si_final.zip
proyecto_final_corregido.zip
```

Esto generaba:

- Desorden total.
- Perdida de trabajo.
- Imposibilidad de saber quien cambio que.
- Riesgo alto de sobreescribir cambios de otros.

Git evita este desorden guardando la historia real del proyecto de forma automatica.

### Ideas Clave

Un sistema de control de versiones permite:

- **Guardar que cambio**: cada modificacion queda registrada.
- **Guardar cuando cambio**: cada cambio tiene fecha y hora.
- **Guardar quien hizo el cambio**: cada modificacion tiene un autor.
- **Volver a versiones anteriores**: si algo sale mal, puedes regresar.
- **Trabajar en equipo**: varias personas pueden modificar el mismo proyecto sin pisarse.

### Conceptos Importantes

#### Historial

Git construye una linea de tiempo del proyecto. Cada punto en esa linea se llama **commit**.

```text
commit 1: crea estructura inicial
commit 2: agrega login
commit 3: corrige validacion
```

#### Recuperacion

Si algo sale mal, puedes volver a un punto anterior sin perder el trabajo actual.

#### Trazabilidad

Puedes saber:

- Quien hizo un cambio.
- Cuando lo hizo.
- Por que lo hizo (mensaje del commit).

### Evolucion De Los Sistemas De Versiones

#### Copias Manuales

Al inicio, las personas guardaban versiones copiando archivos en disquetes, USB o ZIP.

#### Control Centralizado

Luego surgieron sistemas como SVN donde un servidor central guardaba las versiones. Si el servidor se caia, nadie podia trabajar.

#### Control Distribuido (Git)

Git permite que cada persona tenga una copia completa del historial en su maquina. No dependes de un servidor central para trabajar.

### Por Que Git

- **Rapido**: las operaciones son locales.
- **Seguro**: usa hashes SHA-1 para identificar cada commit.
- **Flexible**: permite trabajar offline y sincronizar despues.
- **Estandar de la industria**: usado por millones de desarrolladores.

---

## Git, GitHub Y Ramas

### Que Es Git

Git es un sistema de control de versiones distribuido, creado por Linus Torvalds en 2005.

- Guarda la historia completa del proyecto en tu maquina.
- Permite crear copias de trabajo llamadas **ramas**.
- Funciona sin necesidad de internet.
- Es gratuito y de codigo abierto.

### Que Es GitHub

GitHub es una plataforma en la nube que almacena repositorios de Git.

- Permite compartir tu codigo con otros.
- Facilita la colaboracion en equipo.
- Ofrece herramientas como Pull Requests, Issues y Actions.
- No es lo mismo que Git.

### Diferencia Entre Git Y GitHub

| Git | GitHub |
|---|---|
| Es un software que instalas en tu maquina | Es un servicio web que almacena repositorios |
| Funciona sin internet | Necesita internet para sincronizar |
| Controla versiones localmente | Permite compartir y colaborar |
| Es gratuito y open source | Tiene planes gratuitos y de pago |

**Analogia**: Git es como Microsoft Word instalado en tu PC. GitHub es como Google Docs, donde compartes y trabajas con otros.

### Relacion Entre Git Y GitHub

El flujo basico es:

1. Trabajas en tu maquina con Git.
2. Envias tus cambios a GitHub con `git push`.
3. Otros descargan tus cambios con `git pull`.
4. Todos colaboran en el mismo proyecto.

### Que Es Una Rama

Una rama es una linea de trabajo independiente dentro del mismo repositorio.

- Te permite experimentar sin afectar el codigo principal.
- Puedes crear ramas para nuevas funcionalidades, correcciones o experimentos.
- Las ramas se pueden fusionar despues.

```text
main (rama principal)
  |
  +-- feature/login (rama para login)
  |
  +-- feature/perfil (rama para perfil)
```

### Main Vs Master

Historicamente, la rama principal se llamaba `master`. Desde 2020, la industria adopto `main` como nombre por defecto.

- Ambos cumplen la misma funcion.
- `main` es el estandar actual.
- Git permite renombrar ramas facilmente.

### Loki, Git Y La Linea Temporal Sagrada

Si viste la serie **Loki** de Marvel, entender ramas de Git te resultara mucho mas facil. La serie usa un concepto llamado la **Linea Temporal Sagrada** que es practicamente una analogia perfecta de como funcionan las ramas en Git.

![La Linea Temporal Sagrada del TVA](./imagenes/sacred-timeline.png)

#### La Linea Temporal Sagrada: Un Repositorio Cosmico

Imagina la Linea Temporal Sagrada como un repositorio de Git gigante, mantenido meticulosamente por la **Autoridad de Variacion Temporal (TVA)**, esos burocratas de cara seria dedicados a preservar el flujo "correcto" del tiempo. Cualquier desviacion de esta linea, conocida como **Evento Nexus**, es como un commit rebelde que podria destruir todo el multiverso.

En Git, tu rama `main` es la Linea Temporal Sagrada: es la version estable y oficial de tu proyecto.

#### Loki, El Pull Request Travieso

Loki, nuestro querido Dios del Engaño, es como un desarrollador travieso que sigue enviando pull requests que rompen todo. El es quien accidentalmente borro la rama master de la Linea Temporal Sagrada, causando todo tipo de caos temporal.

En Git, cuando experimentas en una rama y algo sale mal, no destruiste la rama principal. Solo borras la rama experimental y vuelves a `main`.

#### Ramas De Git: Caminos Divergentes Para La Realidad

Las ramas de Git, por otro lado, divergen intencionalmente de la linea temporal principal, permitiendo a los desarrolladores experimentar sin interrumpir la estabilidad del codigo principal. Una vez que los cambios se consideran estables, pueden fusionarse de vuelta a la rama `main`.

```text
main (Linea Temporal Sagrada)
  |
  +-- feature/experimento (Rama alternativa - Loki causo un Evento Nexus)
  |
  +-- fix/correccion (Rama para arreglar un problema)
```

#### Conflictos De Fusion: Dolores De Cabeza Cosmicos

En la Linea Temporal Sagrada, los Eventos Nexus surgen de desviaciones del curso predeterminado de la historia, alterando potencialmente toda la linea temporal. En Git, los **conflictos de fusion** ocurren cuando cambios en diferentes ramas intentan modificar el mismo archivo, requiriendo resolucion manual.

#### Podar Ramas Y El Reset De La TVA

La costumbre de la TVA de podar ramas, o resetear lineas temporales, es como un desarrollador limpiando su repositorio de Git. Se deshacen de ramas viejas y sin usar que solo ocupan espacio y causan desorden.

En Git:

```bash
# Eliminar una rama que ya no necesitas
git branch -d nombre-rama

# Forzar eliminacion si no esta fusionada
git branch -D nombre-rama
```

#### Git Reset: Un Retcon Cosmico

El comando `git reset` es basicamente un retcon cosmico, permitiendo a los desarrolladores reescribir la historia y deshacer sus errores. Pero al igual que con los viajes en el tiempo, es mejor usar este poder con moderacion, o podrias terminar creando paradojas que podrian desenredar la misma tela de la realidad.

```bash
# Cuidado: esto reescribe la historia
git reset --hard HEAD~1
```

**Advertencia**: al igual que la TVA no deberia abusar del reset, tu no deberias abusar de `git reset --hard`. Usalo solo cuando estes seguro de lo que haces.

#### Dos Lineas Temporales, Un Proposito

Ya sea que estes lidiando con Lineas Temporales Sagradas o ramas de Git, el objetivo es el mismo: **mantener el orden y prevenir el caos**. La Linea Temporal Sagrada asegura que la realidad no se descarrile, mientras que las ramas de Git permiten a los desarrolladores experimentar e innovar sin romper todo.

Asi que la proxima vez que trabajes en un proyecto de Git, recuerda que no solo estas gestionando ramas de codigo; eres un **guardian cosmico**, salvaguardando la integridad de tu codigo. Y quien sabe, quizas algun dia la TVA comience a monitorear nuestros repositorios de Git, asegurandose de que no creemos Eventos Nexus que podrian destruir todo el universo del software.

> **Creditos**: Esta analogia esta basada en el articulo *"Loki, Git, and the Cosmic Retcon"* de [Gaurav Trivedi](https://beingtechnicalwriter.com/sacred-timeline-git/). Publicado en [Being Technical Writer](https://beingtechnicalwriter.com/).

---

## Terminal Y Linux Basico

### Por Que Usar La Terminal

Git se maneja principalmente desde la terminal. Aunque existen interfaces graficas, la terminal te da:

- Control total sobre Git.
- Acceso a todas las funciones.
- Mayor velocidad con practica.
- Compatibilidad con servidores y entornos profesionales.

### Relacion Con DevOps

En el flujo DevOps:

- Linux es la base de la mayoria de servidores.
- Git controla los cambios del codigo.
- Docker empaqueta las aplicaciones.
- Ansible automatiza configuraciones.

Saber moverte en la terminal es fundamental para todos estos cursos.

### Comandos Basicos

#### Saber Donde Estas

```bash
pwd
```

Muestra la ruta completa de tu ubicacion actual.

#### Listar Archivos Y Carpetas

```bash
ls
```

Muestra el contenido del directorio actual.

Para ver mas detalles:

```bash
ls -la
```

#### Cambiar De Directorio

```bash
cd nombre-carpeta
```

Para volver al directorio anterior:

```bash
cd ..
```

Para ir a tu home:

```bash
cd ~
```

#### Crear Un Directorio

```bash
mkdir nombre-carpeta
```

#### Crear Un Archivo Vacio

```bash
touch archivo.txt
```

#### Ver El Contenido De Un Archivo

```bash
cat archivo.txt
```

#### Limpiar La Terminal

```bash
clear
```

### Ejemplo De Uso

```bash
pwd
mkdir mi-proyecto
cd mi-proyecto
touch README.md
ls
cat README.md
```

### Recursos Para Practicar

| Recurso | Enlace |
|---|---|
| Practica interactiva de Linux | [KodeKloud Labs](https://kodekloud.com/studio/labs/linux/) |
| Ubuntu CLI Cheat Sheet | [Ver PDF](./recursos/ubuntu-cli-cheat-sheet.pdf) |
| Guia de comandos Linux | [Linux Journey](https://linuxjourney.com/) |

---

## Instalacion Y Configuracion De Git

### Verificar Si Git Esta Instalado

Antes de instalar Git, revisa si ya existe en tu equipo:

```bash
git --version
```

Si aparece una version como `git version 2.43.0`, Git ya esta instalado.

### Instalar Git

#### Windows

1. Descarga el instalador desde [git-scm.com/downloads](https://git-scm.com/downloads).
2. Ejecuta el instalador.
3. Usa las opciones por defecto.
4. Abre **Git Bash** para usar comandos tipo Linux.

#### macOS

```bash
brew install git
```

O descarga desde [git-scm.com/downloads](https://git-scm.com/downloads).

#### Linux (Ubuntu/Debian)

```bash
sudo apt update
sudo apt install git
```

### Configurar Tu Identidad

Git necesita saber quien realiza cada commit.

```bash
git config --global user.name "Tu Nombre"
git config --global user.email "tu@email.com"
```

Esta configuracion se guarda en tu archivo `~/.gitconfig` y se aplica a todos tus repositorios.

### Configurar El Editor Por Defecto

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

### Ver La Configuracion Actual

```bash
git config --list
```

Para consultar un valor especifico:

```bash
git config user.name
git config user.email
```

### Verificar Instalacion

```bash
git --version
git config user.name
git config user.email
```

Si todos los comandos responden correctamente, Git esta listo para usar.

---

## Primer Repositorio Local

### Que Es Un Repositorio Local

Un repositorio local es una carpeta en tu maquina donde Git controla los cambios de los archivos.

- Contiene todo el historial del proyecto.
- Funciona sin necesidad de internet.
- Puedes trabajar en el de forma independiente.

### Que Hace `git init`

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

### Verificar Que El Repositorio Se Creo

```bash
git status
```

Si ves un mensaje como `On branch main` o `No commits yet`, el repositorio esta listo.

### Directorio De Trabajo

El directorio de trabajo es tu carpeta normal con tus archivos. Git observa esta carpeta y detecta cambios.

```text
mi-proyecto/
├── .git/          (carpeta oculta de Git)
├── README.md      (tu archivo)
└── script.py      (tu archivo)
```

### Crear Un Proyecto Desde Cero

```bash
mkdir mi-proyecto
cd mi-proyecto
git init
touch README.md
git status
```

Ahora tienes un repositorio local con un archivo sin registrar.

### Ver Archivos Ocultos

En Windows, activa "Elementos ocultos" en el explorador para ver `.git`.

En Linux/macOS:

```bash
ls -la
```

Veras la carpeta `.git` en la lista.

---

## Estados, Staging Y Commits

### Los Tres Estados De Git

![Los 3 Estados de Git](imagenes/los-3-estados.png)

Git trabaja con tres estados principales:

| Estado | Significado |
|---|---|
| Modificado (Working Directory) | El archivo cambio en tu carpeta de trabajo |
| Preparado (Staging Area) | El archivo esta listo para entrar al proximo commit |
| Confirmado (Repository) | El cambio ya fue guardado en el historial |

> **Diagrama editable**: Puedes abrir y modificar el diagrama en [Excalidraw](https://excalidraw.com/) subiendo el archivo [`estados-git.excalidraw`](./imagenes/estados-git.excalidraw).

```mermaid
flowchart LR
    WD[📁 Working Directory\nDirectorio de Trabajo]
    SA[📦 Staging Area\nArea de Preparacion]
    LR2[💾 Local Repository\nRepositorio Local]

    WD -->|git add| SA
    SA -->|git commit| LR2
    LR2 -->|git checkout| WD
    SA -->|git restore --staged| WD
    LR2 -->|git restore| WD

    style WD fill:#ffcccc,stroke:#cc0000,stroke-width:2px
    style SA fill:#ccffcc,stroke:#00cc00,stroke-width:2px
    style LR2 fill:#ccccff,stroke:#0000cc,stroke-width:2px
```

**Como funciona el flujo**:

1. **Working Directory** (rojo): Creas o modificas archivos aqui. Git detecta los cambios pero no los guarda aun.
2. **Staging Area** (verde): Usas `git add` para preparar los cambios que quieres incluir en el proximo commit.
3. **Local Repository** (azul): Usas `git commit` para guardar permanentemente los cambios preparados en el historial.

**Analogia**:

- **Working Directory**: tu taller donde trabajas en los archivos.
- **Staging Area**: la bandeja donde pones lo que quieres enviar.
- **Repository**: la caja fuerte donde se guarda todo de forma permanente.

### Revisar El Estado Del Proyecto

```bash
git status
```

Este comando muestra:

- Archivos modificados (en rojo).
- Archivos preparados (en verde).
- Rama actual.
- Si hay cambios sin preparar.

**Usalo constantemente** antes y despues de cada accion.

### Preparar Cambios

Para mover archivos del directorio de trabajo al area de staging:

```bash
git add archivo.txt
```

Para preparar todos los cambios a la vez:

```bash
git add .
```

Para preparar archivos de un tipo especifico:

```bash
git add *.md
```

### Verificar Antes De Confirmar

```bash
git status
```

Los archivos en verde estan listos para el commit.

### Crear Un Commit

```bash
git commit -m "Agrega README inicial"
```

Un commit es una foto del proyecto en un momento dado.

- Guarda el estado de todos los archivos preparados.
- Incluye autor, fecha y mensaje.
- Genera un identificador unico (hash SHA-1).

### Ver El Historial

```bash
git log
```

Para ver una version compacta:

```bash
git log --oneline
```

### Commits Atomicos

Cada commit debe representar un solo cambio logico:

- **Bien**: `Agrega validacion de email`
- **Mal**: `cambios varios`

Un commit atomico facilita:

- Revertir cambios especificos.
- Entender el historial.
- Trabajar en equipo.

### Buenos Mensajes De Commit

- Usa imperativo: `Agrega`, `Corrige`, `Elimina`.
- Se conciso pero claro.
- Explica el que y el por que si es necesario.

Ejemplos:

```text
Agrega pagina de login
Corrige error de validacion en formulario
Elimina archivos temporales del repositorio
```

---

## Deshacer Cambios En Git

### Deshacer Modificaciones En Un Archivo

Si modificaste un archivo y quieres volver a la ultima version confirmada:

```bash
git restore archivo.txt
```

Esto descarta los cambios no preparados y restaura el archivo a su ultimo estado en el commit.

### Quitar Un Archivo Del Staging

Si preparaste un archivo por error y quieres sacarlo del area de staging:

```bash
git restore --staged archivo.txt
```

El archivo vuelve al directorio de trabajo pero conserva tus cambios.

### Ver El Estado Despues De Restaurar

```bash
git status
```

### Ejemplo Completo

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

### Si Ya Hiciste Commit

Si el cambio ya fue confirmado con `git commit`, puedes:

#### Ver El Historial

```bash
git log --oneline
```

#### Revertir Un Commit

```bash
git revert <hash-del-commit>
```

Esto crea un nuevo commit que deshace los cambios del commit especificado, sin borrar el historial.

### Resumen De Comandos

| Accion | Comando |
|---|---|
| Descartar cambios en archivo | `git restore archivo.txt` |
| Quitar del staging | `git restore --staged archivo.txt` |
| Revertir un commit | `git revert <hash>` |
| Ver estado | `git status` |

---

## Gitignore Y Buenas Practicas

### Que Es `.gitignore`

`.gitignore` es un archivo de texto que le dice a Git que archivos o carpetas debe ignorar.

Los archivos ignorados:

- No aparecen en `git status`.
- No se pueden preparar con `git add`.
- No se suben al repositorio.

### Que Archivos Ignorar

Ignora archivos que:

- Contienen informacion sensible (contraseñas, tokens, claves).
- Son generados automaticamente (compilados, logs, caches).
- Son especificos de tu maquina (configuraciones locales).
- Son muy pesados o innecesarios (node_modules, dist, build).

### Ejemplos Comunes

```text
# Archivos de entorno
.env
.env.local

# Dependencias
node_modules/
vendor/

# Archivos compilados
*.pyc
*.class
*.o

# Logs
*.log

# IDE
.vscode/
.idea/

# Sistema operativo
.DS_Store
Thumbs.db

# Archivos temporales
*.tmp
*.bak
```

### Crear Un `.gitignore`

```bash
touch .gitignore
```

Edita el archivo y agrega las reglas:

```text
*.log
.env
node_modules/
```

### Verificar Que Funciona

```bash
touch prueba.log
git status
```

Si `prueba.log` no aparece en la lista, `.gitignore` esta funcionando.

### `.gitignore` Global

Puedes crear un archivo global para que aplique a todos tus repositorios:

```bash
git config --global core.excludesFile ~/.gitignore_global
```

Luego crea el archivo `~/.gitignore_global` con tus reglas comunes.

### Buenas Practicas

#### Commits

- Haz commits pequenos y frecuentes.
- Un commit por cambio logico.
- Mensajes claros y descriptivos.

#### `.gitignore`

- Crea `.gitignore` al inicio del proyecto.
- No ignores archivos de configuracion del proyecto (como `package.json`).
- Comparte `.gitignore` en el repositorio.

#### General

- Usa `git status` constantemente.
- Revisa cambios antes de confirmar.
- Mantener el repositorio limpio facilita la colaboracion.
- Nunca subas informacion sensible.

---

## Laboratorio: Primer Flujo Local Con Git

### Objetivo

Practicar el ciclo basico de Git:

```
modificar -> preparar -> confirmar -> revisar
```

### Requisitos

- Git instalado (`git --version`).
- Terminal abierta.
- Configuracion basica (`user.name` y `user.email`).

### Pasos

#### 1. Crear Una Carpeta De Trabajo

```bash
mkdir laboratorio-git
cd laboratorio-git
```

#### 2. Inicializar Git

```bash
git init
```

Verifica con:

```bash
git status
```

#### 3. Crear Un Archivo README

```bash
touch README.md
echo "# Mi Primer Repositorio" >> README.md
```

#### 4. Revisar Estado

```bash
git status
```

Deberias ver `README.md` en rojo (modificado, no preparado).

#### 5. Preparar El Archivo

```bash
git add README.md
```

Verifica:

```bash
git status
```

Ahora `README.md` debe estar en verde (preparado).

#### 6. Crear El Primer Commit

```bash
git commit -m "Agrega README inicial"
```

Verifica:

```bash
git status
git log --oneline
```

#### 7. Modificar El Archivo

```bash
echo "Este es mi primer repositorio con Git." >> README.md
```

Revisa:

```bash
git status
```

#### 8. Preparar Y Confirmar

```bash
git add .
git commit -m "Agrega descripcion al README"
```

Verifica:

```bash
git log --oneline
```

#### 9. Deshacer Un Cambio

Crea un archivo de prueba:

```bash
touch temporal.txt
echo "contenido temporal" >> temporal.txt
```

Preparalo por error:

```bash
git add temporal.txt
git status
```

Quitalo del staging:

```bash
git restore --staged temporal.txt
git status
```

Descarta el cambio:

```bash
git restore temporal.txt
```

#### 10. Crear Un `.gitignore`

```bash
touch .gitignore
echo "*.tmp" >> .gitignore
echo "*.log" >> .gitignore
```

Crea archivos que deben ser ignorados:

```bash
touch prueba.tmp
touch prueba.log
```

Verifica que no aparecen:

```bash
git status
```

#### 11. Commit Final

```bash
git add .gitignore
git commit -m "Agrega gitignore para archivos temporales"
```

#### 12. Verificacion Final

```bash
git status
git log --oneline
```

El repositorio debe estar limpio y con al menos 3 commits.

### Resultado Esperado

Al finalizar, debes tener:

- Un repositorio local funcional.
- Al menos 3 commits con mensajes claros.
- Un `.gitignore` configurado.
- Entendimiento del flujo: modificar, preparar, confirmar.

---

## Material Complementario

| Recurso | Enlace |
|---|---|
| PDF base del material | [Descargar](./material/fundamentos-instalacion-trabajo-local.pdf) |
| Ubuntu CLI Cheat Sheet | [Descargar](./recursos/ubuntu-cli-cheat-sheet.pdf) |
| Practica interactiva de Linux | [KodeKloud Labs](https://kodekloud.com/studio/labs/linux/) |
| Descargar Git | [git-scm.com](https://git-scm.com/downloads) |
| Documentacion oficial de Git | [git-scm.com/doc](https://git-scm.com/doc) |
| Pro Git (libro gratuito) | [git-scm.com/book](https://git-scm.com/book/en/v2) |
