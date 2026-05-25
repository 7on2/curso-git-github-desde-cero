# Terminal Y Linux Basico

## Por Que Usar La Terminal

Git se maneja principalmente desde la terminal. Aunque existen interfaces graficas, la terminal te da:

- Control total sobre Git.
- Acceso a todas las funciones.
- Mayor velocidad con practica.
- Compatibilidad con servidores y entornos profesionales.

## Relacion Con DevOps

En el flujo DevOps:

- Linux es la base de la mayoria de servidores.
- Git controla los cambios del codigo.
- Docker empaqueta las aplicaciones.
- Ansible automatiza configuraciones.

Saber moverte en la terminal es fundamental para trabajar con Git, servidores, contenedores y automatizacion.

### Git Dentro Del Flujo DevOps

```mermaid
flowchart LR
    Linux["Linux\nTerminal"] --> Git["Git\nVersionado"]
    Git --> GitHub["GitHub\nColaboracion"]
    GitHub --> Docker["Docker\nContenedores"]
    Docker --> Ansible["Ansible\nAutomatizacion"]

    style Linux fill:#238636,stroke:#3fb950,color:#fff
    style Git fill:#1f6feb,stroke:#58a6ff,color:#fff
    style GitHub fill:#30363d,stroke:#8b949e,color:#fff
    style Docker fill:#8957e5,stroke:#bc8cff,color:#fff
    style Ansible fill:#da3633,stroke:#f85149,color:#fff
```

## Comandos Basicos

### Saber Donde Estas

```bash
pwd
```

Muestra la ruta completa de tu ubicacion actual.

### Listar Archivos Y Carpetas

```bash
ls
```

Muestra el contenido del directorio actual.

Para ver mas detalles:

```bash
ls -la
```

### Cambiar De Directorio

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

### Crear Un Directorio

```bash
mkdir nombre-carpeta
```

### Crear Un Archivo Vacio

```bash
touch archivo.txt
```

### Ver El Contenido De Un Archivo

```bash
cat archivo.txt
```

### Limpiar La Terminal

```bash
clear
```

## Ejemplo De Uso

```bash
pwd
mkdir mi-proyecto
cd mi-proyecto
touch README.md
ls
cat README.md
```

## Recursos Para Practicar

| Recurso | Enlace |
|---|---|
| Practica interactiva de Linux | [KodeKloud Labs](https://kodekloud.com/studio/labs/linux/) |
| Ubuntu CLI Cheat Sheet | [Ver PDF](../recursos/ubuntu-cli-cheat-sheet.pdf) |
| Guia de comandos Linux | [Linux Journey](https://linuxjourney.com/) |

## Laboratorio Relacionado

- [Terminal y archivos para Git](../laboratorios/terminal-y-archivos-para-git.md): practica rutas, creacion de archivos, lectura de contenido y organizacion de un proyecto base.

---

[&larr; Anterior: Git y GitHub](./04-git-y-github.md) | [Siguiente: Instalacion y configuracion &rarr;](./03-instalacion-configuracion.md)
