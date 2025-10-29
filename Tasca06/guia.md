# T06: Fonaments del servei DNS

## A. Diagnosi Avançada amb `dig` (Linux / macOS)

### Comanda 1: Consulta Bàsica de Registre A
**Comanda:**  
`dig xtec.cat A`

**Anàlisi:**  
- **IP de resposta:** [Indicar IP obtinguda]  
- **TTL:** [Indicar valor TTL]  
- **Servidor que ha respost:** [Indicar servidor]

**Captura:**  
![dig_xtec_cat_A](img/)
**Comanda:**  
`dig tecnocampus.cat NS`

**Anàlisi:**  
- **Servidors de noms autoritatius:**  
  - [Servidor 1]  
  - [Servidor 2]  
  - [etc.]

**Captura:**  
![dig_tecnocampus_cat_NS]()
**Comanda:**  
`dig escolapia.cat SOA`

**Anàlisi:**  
- **Correu de l'administrador:** [Indicar correu]  
- **Número de sèrie del domini:** [Indicar número]

**Captura:**  
![dig_escolapia_cat_SOA]()
**Comanda:**  
`dig -x 147.83.2.135`

**Anàlisi:**  
- **Informació obtinguda:** [Detallar registre PTR o altra informació]

**Captura:**  
![dig_reverse_147_83_2_135]()

## B. Comprovació de Resolució amb `nslookup` (Multiplataforma)

### Comanda 1: Consulta Bàsica no Autoritativa

**Comandes:**
`nslookup
 set type=A
 tecnocampus.cat`
 
 **Anàlisi:**
- La resposta és **no autoritativa** perquè prové d’un servidor de noms que no és autoritari per al domini consultat.
- Això significa que el servidor ha obtingut la informació d’un altre servidor i no és la font original.

**Captura:**
!nslookup_tecnocampus_cat_no_autoritat

---

## Comanda 2: Consulta Autoritativa

**Comandes:**
`nslookup`

`server [IP del servidor NS autoritatiu obtingut amb dig]
set type=A
tecnocampus.cat`
**Anàlisi:**
- La resposta és **autoritativa** perquè prové directament d’un servidor de noms que gestiona el domini tecnocampus.cat.
- Les diferències respecte a la consulta anterior inclouen:
  - Informació més precisa i directa.
  - Possiblement més detalls en els registres.
  - Confirmació que el servidor és responsable del domini.

**Captura:**
!nslookup_tecnocampus_cat_autoritat

## C. Resolució Local

### Activitat: Comprovació del funcionament de la resolució local

La resolució local permet associar noms d’equip amb adreces IP dins d’una xarxa interna, sense necessitat de consultar un servidor DNS extern. Això és útil en entorns on no es disposa d’un servidor de noms propi.

#### Exemple de configuració

**Fitxer modificat:** `/etc/hosts` (en sistemes Linux/macOS)

**Entrada afegida:**
 `192.168.1.100 servidorlocal`
 #### Comanda de prova
 `ping servidorlocal`
 
 #### Anàlisi:
- Si la resolució local funciona correctament, el sistema reconeix el nom `servidorlocal` i l’associa a la IP `192.168.1.100`.
- No es fa cap consulta externa al DNS.
- És una solució ràpida i eficaç per a entorns petits o temporals.

**Captura:**
!ping_servidorlocal

 
