# Git y GitHub Desde Cero

![Git](https://img.shields.io/badge/Git-Fundamentos-orange)
![GitHub](https://img.shields.io/badge/GitHub-Desde%20Cero-black)
![Nivel](https://img.shields.io/badge/Nivel-Inicial-brightgreen)
![Estado](https://img.shields.io/badge/Estado-En%20Curso-blue)

Aprende Git y GitHub desde fundamentos hasta flujos colaborativos reales, con explicaciones simples, comandos practicos y laboratorios para practicar desde casa.

## Ruta De Aprendizaje

| Bloque | Tema | Ir |
|---|---|---|
| 01 | Fundamentos de control de versiones | [Abrir](./clases/01-fundamentos.md) |
| 02 | Git y GitHub | [Abrir](./clases/04-git-y-github.md) |
| 03 | Terminal y Linux basico | [Abrir](./clases/02-terminal-linux.md) |
| 04 | Instalacion y configuracion de Git | [Abrir](./clases/03-instalacion-configuracion.md) |
| 05 | Primer repositorio local | [Abrir](./clases/05-repositorio-local.md) |
| 06 | Estados, staging y commits | [Abrir](./clases/06-estados-staging-commits.md) |
| 07 | Deshacer cambios en Git | [Abrir](./clases/07-deshacer-cambios.md) |
| 08 | .gitignore y buenas practicas | [Abrir](./clases/08-gitignore.md) |
| 09 | Ramas en Git | [Abrir](./clases/10-ramas.md) |
| 10 | Merge y conflictos | [Abrir](./clases/11-merge-conflictos.md) |
| 11 | Historial, inspeccion y deshacer con criterio | [Abrir](./clases/09-historial-revert.md) |
| Bonus | Loki y la Linea Temporal Sagrada | [Abrir](./clases/12-bonus-loki.md) |

> El indice sigue la linea del PPT: introduccion, entorno Git, flujo local, ramas/merge/conflictos e historial/deshacer.

### Mapa Rapido De La Guia

```mermaid
flowchart LR
    A["Fundamentos"] --> D["Git y GitHub"]
    D --> B["Terminal"]
    B --> C["Instalacion"]
    C --> E["Repositorio local"]
    E --> F["Staging y commits"]
    F --> G["Deshacer cambios"]
    G --> H["Gitignore"]
    H --> J["Ramas"]
    J --> K["Merge y conflictos"]
    K --> I["Historial y revert"]

    style A fill:#1f6feb,stroke:#58a6ff,color:#fff
    style B fill:#238636,stroke:#3fb950,color:#fff
    style C fill:#8957e5,stroke:#bc8cff,color:#fff
    style D fill:#30363d,stroke:#8b949e,color:#fff
    style E fill:#1f6feb,stroke:#58a6ff,color:#fff
    style F fill:#9e6a03,stroke:#d29922,color:#fff
    style G fill:#da3633,stroke:#f85149,color:#fff
    style H fill:#238636,stroke:#3fb950,color:#fff
    style I fill:#30363d,stroke:#8b949e,color:#fff
    style J fill:#1f6feb,stroke:#58a6ff,color:#fff
    style K fill:#8957e5,stroke:#bc8cff,color:#fff
```

## Laboratorio

| Laboratorio | Descripcion | Ir |
|---|---|---|
| Primer flujo local con Git | Practica el ciclo basico: modificar, preparar, confirmar | [Abrir](./laboratorios/primer-flujo-local-con-git.md) |

## Material De Apoyo

| Material | Descripcion |
|---|---|
| [Guia visual completa](./material/programa-completo-git-y-github-9na-edicion.pdf) | Presentacion de apoyo con fundamentos, flujo local, ramas, merge, conflictos, historial, reset y `git revert`. |

## Recursos Complementarios

| Recurso | Enlace |
|---|---|
| Ubuntu CLI Cheat Sheet | [Ver PDF](./recursos/ubuntu-cli-cheat-sheet.pdf) |
| Practica interactiva de Linux | [KodeKloud Labs](https://kodekloud.com/studio/labs/linux/) |
| Descargar Git | [git-scm.com](https://git-scm.com/downloads) |
| Documentacion oficial de Git | [git-scm.com/doc](https://git-scm.com/doc) |
| Pro Git (libro gratuito) | [git-scm.com/book](https://git-scm.com/book/en/v2) |

El contenido principal de esta guia llega hasta `git revert`. Los temas como `rebase`, `stash`, `cherry-pick`, `reflog` y hooks quedan propuestos como ampliacion para quien quiera seguir profundizando.
