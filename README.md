# Eines de Galindo grup

Tres eines internes per a la gestoria, publicades a GitHub Pages:

- **Venciments**: pòlisses per data de venciment, amb el termini perquè el client les pugui donar de baixa (un mes abans, art. 22 de la Llei de contracte d'assegurança).
- **Trimestrals**: estat dels models 303, 130, 111, 115 i 202 de cada client, amb els terminis de presentació i de domiciliació.
- **Caducitats**: certificats digitals, DNI, carnets de conduir i ITV dels clients.

Enllaç: https://roninsilent.github.io/galindo-eines/

## On són les dades

Aquest repositori és públic, però **no conté cap dada de clients**. Les dades es guarden en un full de càlcul privat al Drive del compte `zenkai3dstudio@gmail.com`, compartit només amb els comptes autoritzats. Cada eina hi entra amb el compte de Google de qui la fa servir; si el compte no té permís sobre el full, no veu res.

Cada eina té la seva pestanya al full (`venciments`, `trimestrals_clients`, `trimestrals_estat`, `caducitats`). No en canviïs els noms ni els de les columnes.

## Configuració de l'accés a Google

El fitxer `config.js` necessita l'identificador d'un client OAuth. Es crea una sola vegada a Google Cloud amb el compte `zenkai3dstudio@gmail.com`:

1. A [console.cloud.google.com](https://console.cloud.google.com), crea un projecte nou (per exemple, «Galindo eines»).
2. A **APIs i serveis → Biblioteca**, activa la **Google Sheets API**.
3. A **Google Auth Platform**, configura la pantalla de consentiment: tipus **Extern**, nom «Galindo grup · eines».
4. A **Públic**, deixa l'aplicació en mode **Prova** i afegeix com a usuaris de prova els comptes que hi han d'entrar.
5. A **Clients**, crea un client de tipus **Aplicació web** amb l'origen JavaScript autoritzat `https://roninsilent.github.io`.
6. Copia l'identificador del client (acaba en `.apps.googleusercontent.com`) i posa'l a `clientId` dins de `config.js`.

En mode Prova, només els usuaris de prova poden entrar. Google mostrarà un avís d'aplicació no verificada la primera vegada: cal tocar «Continua».

## Codi

Les pàgines són HTML autònom, sense dependències ni compilació. Es generen des d'un script de construcció comú; si les edites a mà, recorda que les tres comparteixen estils i funcions.
