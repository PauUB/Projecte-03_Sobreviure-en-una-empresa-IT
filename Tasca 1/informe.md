# **Fase 1: Anàlisi i Justificació**  
## **Informe Tècnic – Gestors de Contrasenyes**

### **1. Introducció i Justificació**

Les **contrasenyes febles o reutilitzades** són un risc crític per a l’empresa, ja que faciliten atacs com el **diccionari**, el **brute force** o el **credential stuffing**.  
Un **gestor de contrasenyes** redueix aquests riscos permetent generar i guardar contrasenyes segures de manera xifrada, evitant errors humans i millorant la seguretat general.

---

### **2. Comparativa Tècnica**

| **Criteri** | **Bitwarden (Online)** | **KeePassXC (Offline)** |
|--------------|------------------------|--------------------------|
| **Model** | Núvol (xifratge end-to-end) | Local (fitxer `.kdbx`) |
| **Sincronització** | Automàtica entre dispositius | Manual o via serveis externs |
| **Accés** | Web, escriptori i mòbil | Escriptori (versió portable) |
| **Codi** | Open source | Open source |
| **Cost** | Freemium (plans d’empresa) | Gratuït |
| **Gestió corporativa** | Centralitzada amb SSO i 2FA | No integrada |
| **Dependència del núvol** | Sí (opció autohosting) | No |

---

### **3. Avantatges i Inconvenients**

| **Bitwarden** | **KeePassXC** |
|----------------|----------------|
| ✅ Sincronització i facilitat d’ús. | ✅ Total control local. |
| ✅ Integració corporativa. | ✅ Sense costos. |
| ⚠️ Dependència del núvol. | ⚠️ Sense sincronització automàtica ni gestió centralitzada. |

---

### **4. Recomanació**

Es recomana **Bitwarden** per al personal tècnic, ja que combina **seguretat, usabilitat i gestió centralitzada**, facilitant la sincronització entre dispositius i la protecció de credencials amb **xifratge end-to-end**.  
**KeePassXC** és una bona alternativa per a entorns individuals o sense connexió al núvol.

