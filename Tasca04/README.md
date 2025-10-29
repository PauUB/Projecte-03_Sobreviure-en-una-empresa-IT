# T04: Serveis de Directori - LDAP a Innovatech

## 🧩 Context

Innovatech, una start-up tecnològica en ràpid creixement, pateix problemes greus en la gestió d'usuaris i accessos:
- Bases de dades d'usuaris separades per cada servei.
- Autenticació local als clients.
- Ineficiència operativa, risc de seguretat i manca d'escalabilitat.

## 🎯 Objectiu

Implementar una solució d’autenticació centralitzada mitjançant **OpenLDAP** en un servidor GNU/Linux, per:
- Centralitzar la gestió d'usuaris i grups.
- Facilitar l'accés a serveis de xarxa.
- Millorar la seguretat i escalabilitat.

## 🛠️ Tasques a Desenvolupar

1. **Instal·lació del servidor OpenLDAP**
   - Paquets necessaris
   - Verificació del servei

2. **Configuració del domini base**
   - Definició del DN (Distinguished Name)
   - Fitxers de configuració

3. **Creació de la jerarquia LDAP**
   - Unitats organitzatives (OU): usuaris, grups, serveis
   - Estructura del directori

4. **Integració d'usuaris i grups**
   - Creació d'entrades LDIF
   - Importació al directori

5. **Configuració del client LDAP**
   - Autenticació contra el servidor LDAP
   - Verificació de l'accés
     
## 🧪 Proves i Validació

- Test d'autenticació des de clients
- Accés a serveis amb usuaris LDAP
- Eliminació/creació d'usuaris i propagació


