# T04: Serveis de directori. LDAP

## Instal·lació OpenLDAP

- La xarxa tindrà dues interfícies una en xarxaNAT i l'altra en host-only

- El primer pas és instal·lar ldap-utils

![instal·lació ldap](img/img1.png)

- Ara configurarem la contrassenya del servei

![contrassenya ldap:p@ssw0rd](img/img2.png)

- Comprovem que el servei funciona correctament

![Comprovació servei](img/img3.png)

- Ara comprovem que el directori s'ha crteat amb el nom correcte

![Comprovació del directori](img/img4.png)

- Creem els OU d'users i de groups

![Creació d'OU](img/img5.png)

- Comprovem que s'hagi creat correctament

  ![comprovació](img/img7.png)

  ---

  ## Configuració directori usant LAM

  - Anirem a LDAP account manager

  ![LDAP account manager](img/img8.png)

  - Ems dirigim a *LAM configuration* i un cop allà anem a *Edit server profiles* amb el password lam

  ![LAM](img/img9.png)
  
  ![LAM](img/img10.png)

- Primeres configuracions: idioma, compte admin, etc.

![configuracions bàsiques](img/img11.png)

![configuracions bàsiques](img/img12.png)

![configuracions bàsiques](img/img14.png)

- Ara accedirem al directori
  
![Accés directori](img/img13.png)

- Un cop haver-hi accedit creem els grups tech i manager
  
![Creació grup tech](img/img15.png)

![Creació grup manager](img/img16.png)

![Comprovació dels grups](img/img17.png)

- Creem els usuaris tech01 i manager01
  
![creació usuari tech01](img/img18.png)

![creació usuari tech01](img/img19.png)

![creació usuari tech01](img/img20.png)

![creació usuari manager01](img/img21.png)

![creació usuari manager01](img/img22.png)

![creació usuari manager01](img/img23.png)

---

##  Autenticació utilitzant LDAP

- Configurem el nom del client per tal de que sigui del domini corresponent del directori modificant l'arxiu `/etc/hosts`

![entrem a l'arxiu hosts](img/img24.png)

- Instal·lem libpam i nss

![Instal·lació](img/img32.png)

- Ara farem la configuració

![configuració](img/img25.png)

![configuració](img/img26.png)

![configuració](img/img27.png)

![configuració](img/img28.png)

![configuració](img/img29.png)

![configuració](img/img30.png)

![configuració](img/img31.png)

- Des del client comprovem si es connecta al servidor

![comprovació client-servidor](img/img33.png)

- Configurem l'arxiu nsswitch.conf per indicar que s'usarà ldap per usuaris i grups

![modificació arxiu](img/img34.png)

- Eliminem la línia use_authtok a l'arxiu /etc/pam.d/common-password

![eliminació línia](img/img35.png)

![eliminació línia](img/img36.png)

- Ara editem l'arxiu /etc/pam.d/common-session i afagim la linia per a crear els perfils

![creació de la línia](img/img37.png)

- Reiniciem el servei amb
  ```bash
  systemctl restart nscd
  ```
- Comprovem que veu els usuaris LDAP

![Comprovació](img/img38.png)

- Per finalitzar editem l'arxiu /etc/pam.d/gdm-launch-environment

![edició arxiu](img/img39.png)

- Reiniciem el client i provem a iniciar sessió amb un dels usuaris del directori

![sessió tech01](img/img40.png)

![sessió tech01](img/img41.png)

- Un cop iniciem sessió comprovem com se li ha creat la carpeta personal i comprovem l'usuari

![Comprovació final](img/img42.png)

  
