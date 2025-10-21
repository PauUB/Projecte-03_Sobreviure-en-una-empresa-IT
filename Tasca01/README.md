# 🔐 Context de la situació

La consultora **EverPia**, on els becaris estan fent pràctiques, ha patit un **atac informàtic greu**. Els ciberdelinqüents han accedit a informació confidencial d’un projecte en desenvolupament i amenacen amb fer-la pública si no es paga un rescat.  

La situació ha generat una gran alarma dins l’empresa, que ha activat un **comitè de crisi** per gestionar l’incident.  
La investigació interna ha revelat que l’origen de l’atac ha estat la **compromisió d’un compte tècnic** a causa de l’ús d’una **contrasenya feble o reutilitzada**, un error habitual però molt perillós.

---

## 🛡️ Resposta de l’empresa

Davant d’aquesta crisi, la **Direcció Tècnica** ha decidit que tot el personal tècnic ha de començar a **utilitzar un gestor de contrasenyes validat**, per garantir que les credencials siguin robustes, úniques i segures.

---

## 📘 Tasca assignada als becaris

Els becaris han de dur a terme una **tasca individual** dividida en **dues fases**:

---

### 🧩 Fase 1: Informe tècnic (`informe.md`)

Cal redactar un document que justifiqui tècnicament la decisió de la Direcció i compari les opcions disponibles.  
L’informe ha d’incloure:

#### **1. Introducció i Justificació**

- Explicació del risc que suposen les contrasenyes febles o reutilitzades (atacs com *credential stuffing*, *diccionari*, etc.).
- Paper clau dels gestors de contrasenyes per mitigar aquests riscos.

#### **2. Comparativa Tècnica**

**Bitwarden (alternativa online):**
- Sincronització entre dispositius.  
- Xifratge de punta a punta.  
- Accés multiplataforma.  
- Model freemium i cost.

**KeePassX / KeePassXC (alternativa offline):**
- Emmagatzematge local (fitxer KDBX).  
- Independència del núvol.  
- Codi obert.  
- Portabilitat del fitxer.

#### **3. Avantatges i Inconvenients**

Comparació entre models **online** i **offline** en termes de:
- Seguretat  
- Usabilitat  
- Continuïtat del negoci

#### **4. Recomanació Final**

- Elecció de l’eina més adequada per al personal tècnic.  
- Justificació de la decisió.

---

### 🧭 Fase 2: Guia d’ús tècnica (`guia.md`)

Un cop escollida l’eina (*Bitwarden*, *KeePassXC* o similar), cal crear una **guia clara i visual** per formar l’equip tècnic.  
Ha d’incloure:

#### **1. Instal·lació i Configuració Inicial**

- Descàrrega i instal·lació.  
- Creació del compte mestre o base de dades principal.

#### **2. Generació de Contrasenyes Segures**

- Ús del generador de contrasenyes.  
- Paràmetres: longitud, caràcters especials, etc.

#### **3. Exemples d’Ús i Emplenament Automàtic**

- Desar credencials de correu electrònic.  
- Desar credencials d’aplicacions o serveis web.  
- Ús de l’extensió del navegador per emplenar automàticament.

#### **4. Gestió de Còpies de Seguretat**

- Com fer còpies de seguretat (exportació o fitxer KDBX).  
- Recomanacions per emmagatzemar-les de forma segura (USB xifrat, núvol xifrat).

---

## 📁 Lliurament de la tasca

Dins el **repositori del projecte-3**, cal crear la carpeta `tasca01` amb:

- `README.md`: descripció de la tasca i enllaços als arxius.  
- `informe.md`: informe tècnic de la fase 1.  
- `guia.md`: guia d’ús de la fase 2.  
- Carpeta d’imatges (`img`, `pics`, etc.) per les captures de pantalla de la guia.

---

## 📚 Materials de suport

- [INCIBE: Gestió de contrasenyes segures](https://www.incibe.es/)  
- [Pàgina oficial de Bitwarden](https://bitwarden.com/)  
- [Pàgina oficial de KeePassXC](https://keepassxc.org/)  
- [INCIBE: Gestors de contrasenyes i com milloren la seguretat empresarial](https://www.incibe.es/)
