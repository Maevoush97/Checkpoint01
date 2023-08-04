# Checkpoint01
## 1.1: Eléments du réseau :
| Questions | Réponses |
|---        |:-:       |
|Différences entre le matériel B et le matériel A |           |
|Que représentent em0, em1 et em2 ? | Ce sont les __interfaces du routeur__. Ici __em0__ sert de connexion entre le __WAN et le routeur__, __em1__ lui, sert de connexion entre __le routeur et l'interface LAN__            |
|Que signifie /26 ? |  Il s'agit du __masque de sous-réseau__ (*ici écrit en notation CIDR*) qui indique la partie réseau et la partie machine d'une adresse IP, ici il y a 26 "1" dans la partie réseau et 6 "0" dans la partie machine (car 26+6=32 et adresse IP en 32bits)             |
|Dans le vocabulaire IP, qu'est-ce qu'Ubuntu-1, Ubuntu-2 ... ? | Ce sont des __hôtes VPCS__  (*des ordinateurs virtuels*)       |
|Et A et B ? |   A est un __switch__ (*commutateur*) et B est un __routeur__       |
|Peut-on considérer qu'Ubuntu-2 soit directement connecté en em1 de l'équipement pfSense ? |  Non, car Ubuntu-2 doit d'abord passer par le switch, qui fonctionne comme un pont       |


## 1.2: Etude théorique :
__*Par rapport aux adresses IP de chaque PC :*__
| Questions | Réponses |
|--- |:-: |
|Adresse de diffusion du réseau 1 |         |
|Plage d'adresses disponibles du réseau 1 |          |
|Adresse de diffusion du réseau 2 | L'adresse de diffusion du réseau 2 est __*10.0.0.255*__      |
|Plage d'adresses disponibles du réseau 2 |  La plage d'adresses disponibles est __*253*__ (car l'adresse 10.0.0.0 sera l'adresse réseau et ne peux pas être distribuer à un équipement)    |
|Les machines Ubuntu-1 et Ubuntu-2 peuvent-elles communiquer entre-elles ? Pourquoi ? |   Non car étant dans des réseaux différents, elles ont besoin d'un pont pour pouvoir communiquer entre elles      |
|Quelles machines vont pouvoir __*sortir*__ du réseau ? |         |
|Pour passer les adresses IP des machines en dynamique, doit-on ajouter des éléments au schéma pour que cela soit possible ? (2 situations possibles) |   On peut ajouter 1 pont, ou           |


## 1.3: Analyse de trames :
### *Fichier 1*
| Questions | Réponses |
|--- |:-: |
|Dans cette trame, qui initialise la communication ? |  Le paquet N°1       |
|La communication est-elle réussie ? Si oui, entre quels matétiels et si non expliquer pourquoi |  Oui la communication entre le paquet N°1 et le paquet N°2 a bien réussie          |
|A qui correspond le request et le reply dans toute la trame ? | Le __request__ correspond à l'adresse IP *10.10.4.2*  et le __reply__ correspond à l'adresse IP *10.10.4.1*       |
|Quels sont les rôles des matériels A et B ? | A est le demandeur et B est le broadcast          |

### *Fichier 2*
| Questions | Réponses |
|--- |:-: |
|Qui initialise la communication ? |  Le paquet N°1 initialise la communication (*IP 10.10.80.3*)          |
|A-t-elle réussie ? Si oui entre quels matériels, et si non expliquer pourquoi |   Non, la communication entre les 2 adresses IP n'a pas réussie      |
|Expliquer les rôles des matériels A et B |         |

### *Fichier 3*
| Questions | Réponses |
|--- |:-: |
|Qui initialise la communication ? |   Le paquet N°2      |
|Celle-ci a-t-elle réussie ? Si oui entre quels matériels et si non expliquer pourquoi |           |
|Quels sont les rôles des matériels A et B ? |                |
|Où vois-tu les différents protocoles encapsulés ? |           |
