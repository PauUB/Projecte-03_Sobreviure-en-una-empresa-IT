
# T03: Gestió flexible de discos (LVM i Espais d’emmagatzematge)

Un cop completada la fase de formació, el repte és dissenyar i documentar dues solucions d'emmagatzematge per al nostre client **Garriga i Associats**, un bufet d'advocats que gestiona informació legal sensible. Els requisits principals són:

- **Integritat i protecció contra fallades**
- **Alta disponibilitat i redundància**
- **Escalabilitat sense interrupcions**
- **Facilitat de gestió**

## Objectiu
Crear una **prova de concepte** amb màquines virtuals que mostri dues implementacions:

### 1. Entorn Linux (Zorin OS) – LVM
- Creació de grups i volums lògics
- Configuració de mirall (`lvm_mirror`)
- Instantànies (snapshots) i restauració
- Ampliació de volums per demostrar escalabilitat

### 2. Entorn Windows (Windows 11) – Storage Spaces
- Creació d'un Storage Pool amb discos simulats
- Configuració de resiliència:
  - **Mirroring**
  - **Parity**
  - **Mirall triple**
- Visualització i gestió des de la consola

## Lliurables
- Documentació en **Markdown** amb imatges i explicacions dins la carpeta `tasca03`
- **README.md** amb:
  - Descripció de la tasca
  - Enllaços als dos documents:
    - Solució Linux (LVM)
    - [Solució Windows (StorageSpaces)

> **Nota:** El treball és en grup, amb divisió per equips (Linux / Windows). La nota és conjunta, així que cal una bona coordinació.

