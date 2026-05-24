# Fundamentos Del Control De Versiones

## Que Problema Resuelve

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

## Ideas Clave

Un sistema de control de versiones permite:

- **Guardar que cambio**: cada modificacion queda registrada.
- **Guardar cuando cambio**: cada cambio tiene fecha y hora.
- **Guardar quien hizo el cambio**: cada modificacion tiene un autor.
- **Volver a versiones anteriores**: si algo sale mal, puedes regresar.
- **Trabajar en equipo**: varias personas pueden modificar el mismo proyecto sin pisarse.

## Conceptos Importantes

### Historial

Git construye una linea de tiempo del proyecto. Cada punto en esa linea se llama **commit**.

```text
commit 1: crea estructura inicial
commit 2: agrega login
commit 3: corrige validacion
```

### Historial Como Linea De Tiempo

```mermaid
flowchart LR
    A["Commit 1\nCrea estructura"] --> B["Commit 2\nAgrega login"]
    B --> C["Commit 3\nCorrige validacion"]
    C --> D["Estado actual"]

    style A fill:#1f6feb,stroke:#58a6ff,color:#fff
    style B fill:#1f6feb,stroke:#58a6ff,color:#fff
    style C fill:#1f6feb,stroke:#58a6ff,color:#fff
    style D fill:#238636,stroke:#3fb950,color:#fff
```

### Recuperacion

Si algo sale mal, puedes volver a un punto anterior sin perder el trabajo actual.

### Trazabilidad

Puedes saber:

- Quien hizo un cambio.
- Cuando lo hizo.
- Por que lo hizo (mensaje del commit).

## Evolucion De Los Sistemas De Versiones

### Copias Manuales

Al inicio, las personas guardaban versiones copiando archivos en disquetes, USB o ZIP.

### Control Centralizado

Luego surgieron sistemas como SVN donde un servidor central guardaba las versiones. Si el servidor se caia, nadie podia trabajar.

### Control Distribuido (Git)

Git permite que cada persona tenga una copia completa del historial en su maquina. No dependes de un servidor central para trabajar.

## Por Que Git

- **Rapido**: las operaciones son locales.
- **Seguro**: usa hashes SHA-1 para identificar cada commit.
- **Flexible**: permite trabajar offline y sincronizar despues.
- **Estandar de la industria**: usado por millones de desarrolladores.

---

[Siguiente: Git y GitHub &rarr;](./04-git-y-github.md)
