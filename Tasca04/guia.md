# 🧩 T04: Serveis de Directori – LDAP

## 🛠️ 1. Instal·lació d’OpenLDAP

- La màquina tindrà **dues interfícies de xarxa**:
  - Una en **xarxa NAT**
  - Una altra en **host-only**

- Instal·lem el paquet **`ldap-utils`**:

![Instal·lació ldap](img/img1.png)

- Durant la configuració, establim la **contrasenya del servei LDAP** (`p@ssw0rd`):

![Contrasenya ldap](img/img2.png)

- Comprovem que el **servei LDAP s’està executant correctament**:

![Comprovació servei](img/img3.png)

- Verifiquem que el **directori s’ha creat amb el nom correcte**:

![Comprovació del directori](img/img4.png)

- Creem les **Unitats Organitzatives (OU)** per a *users* i *groups*:

![Creació d'OU](img/img5.png)

- Comprovem que s’han creat correctament:

![Comprovació OU](img/img7.png)

---

## ⚙️ 2. Configuració del directori amb LDAP Account Manager (LAM)

- Obrim el **LDAP Account Manager**:

![LDAP account manager](img/img8.png)

- Accedim a:
  **LAM Configuration → Edit server profiles**
  i entrem amb la contrasenya `lam`.

![LAM configuració](img/img9.png)
![LAM configuració](img/img10.png)

- Configurem els **paràmetres bàsics**: idioma, compte administrador, etc.

![Configuracions bàsiques](img/img11.png)
![Configuracions bàsiques](img/img12.png)
![Configuracions bàsiques](img/img14.png)

- Accedim al **directori LDAP**:

![Accés al directori](img/img13.png)

- Creem els **grups** `tech` i `manager`:

![Creació grup tech](img/img15.png)
![Creació grup manager](img/img16.png)
![Comprovació grups](img/img17.png)

- Creem els **usuaris** `tech01` i `manager01`:

![Creació usuari tech01](img/img18.png)
![Creació usuari tech01](img/img19.png)
![Creació usuari tech01](img/img20.png)
![Creació usuari manager01](img/img21.png)
![Creació usuari manager01](img/img22.png)
![Creació usuari manager01](img/img23.png)

---

## 🔐 3. Autenticació utilitzant LDAP

- Configurem el **nom del client** per associar-lo al domini del directori, editant l’arxiu `/etc/hosts`:

![Edició hosts](img/img24.png)

- Instal·lem els paquets necessaris:

```bash
sudo apt install libpam-ldap libnss-ldap nscd

```
![Instal·lació](img/img32.png)

- Realitzarem la **configuració del client LDAP**:

![configuració](img/img25.png)

![configuració](img/img26.png)

![configuració](img/img27.png)

![configuració](img/img28.png)

![configuració](img/img29.png)

![configuració](img/img30.png)

![configuració](img/img31.png)

- Comprovem la **connexió entre el client i el servidor**:

![comprovació client-servidor](img/img33.png)

- Editem l’arxiu `/etc/nsswitch.conf` per indicar que s’utilitzarà LDAP per a usuaris i grups:

```bash

passwd:         files systemd ldap
group:          files systemd ldap
shadow:         files ldap
```
![modificació arxiu](img/img34.png)

- Eliminem la línia `use_authtok ` de l’arxiu `/etc/pam.d/common-password`:


![eliminació línia](img/img35.png)

![eliminació línia](img/img36.png)

- Editem l’arxiu `/etc/pam.d/common-session` i afegim la línia següent per crear automàticament els directoris personals dels usuaris:

```bash
session required pam_mkhomedir.so skel=/etc/skel umask=0022
```
![creació de la línia](img/img37.png)

- Reiniciem el servei de memòria cau d’usuaris:


```bash
sudo sysstemctl restart nscd
```
- Comprovem que el sistema **detecta els usuaris LDAP**:
![Comprovació usuaris LDAP](img/img38.png)

- Editem l’arxiu `/etc/pam.d/gdm-launch-environment` per assegurar l’autenticació gràfica:

![edició arxiu](img/img39.png)

- Reiniciem el client i **iniciem sessió amb un usuari del directori** (`tech01`, per exemple):
![sessió tech01](img/img40.png)

![sessió tech01](img/img41.png)

- Un cop iniciada la sessió, comprovem que:


  - S’ha creat la **carpeta personal de l’usuari**

  - L’usuari s’ha **autenticat correctament via LDAP**


![Comprovació final](img/img42.png)

  
