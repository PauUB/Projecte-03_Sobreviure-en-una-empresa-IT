# 📘 Auditoria DNS per a DigiCore

## 🧭 Introducció
Aquest projecte forma part d'una col·laboració entre EverPia i DigiCore, una empresa de màrqueting digital que experimenta problemes de connectivitat. L'objectiu és auditar el servei DNS i formar el personal tècnic del client per millorar la seva capacitat de diagnosi.

## 👥 Equip Tècnic
- Consultora: EverPia

## 🗂 Estructura del Projecte
fase_teorica/         # Materials formatius

fase_practica/        # Scripts, captures i anàlisi CLI

guia.md               # Document amb resultats i explicacions

video_formatiu/       # Píndola formativa en vídeo

---

## 📚 Fase Teòrica: Formació DNS

### 🎯 Objectiu
Dotar el personal tècnic de DigiCore amb coneixements sòlids sobre el funcionament del DNS.

### 📑 Continguts Formatius
- **Jerarquia i Estructura del DNS**
  - Root, TLDs, dominis de segon nivell
- **Procés de Resolució**
  - Consultes iteratives vs recursives
  - Servidors Root i autoritatius
- **Tipus de Zones**
  - Directa vs inversa
  - Zona primària vs secundària
- **Tipus de Registres DNS**
  - A, CNAME, MX, NS, SRV
- **Conceptes Essencials**
  - Resposta autoritativa
  - TTL
  - SOA
  - Reenviadors (condicionals/incondicionals)
  - Resolució local i mDNS

### 🎥 Activitat
- Creació d’un vídeo formatiu (10-15 min)
- Explicació clara i concisa dels conceptes anteriors

---

## 🛠 Fase Pràctica: Diagnosi amb CLI

### 🖥️ Entorn de Treball
- Equip Zorin OS amb doble interfície (NAT + pont)
- IP configurada segons indicacions

### 🧪 Eines i Comandes

#### 🔍 Diagnosi amb `dig` (Linux/macOS)
1. `dig xtec.cat A`  
   → IP, TTL, servidor de resposta
2. `dig tecnocampus.cat NS`  
   → Servidors autoritatius
3. `dig escolapia.cat SOA`  
   → Correu admin, número de sèrie
4. `dig -x 147.83.2.135`  
   → Resolució inversa

#### 🧭 Diagnosi amb `nslookup` (Multiplataforma)
1. Consulta no autoritativa  
   - `set type=A` → tecnocampus.cat
2. Consulta autoritativa  
   - `server IP` → tecnocampus.cat

#### 🧷 Resolució Local
- Protocol mDNS
- Mecanismes sense servidor

### 📄 Activitat
- Creació del document `guia.md`
- Incloure:
  - Captures de pantalla de les comandes
  - Anàlisi i explicació dels resultats

---

## ✅ Resultats Esperats
- Formació efectiva del personal tècnic de DigiCore
- Guia pràctica per a diagnosi ràpida de problemes DNS
- Millora en la capacitat de resolució d’incidències

## 📌 Notes Addicionals
- Recomanacions per a manteniment DNS
- Recursos addicionals (enllaços, manuals, RFCs)
