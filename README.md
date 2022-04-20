# switching
![switching](https://user-images.githubusercontent.com/83721477/164189484-72234b9b-2cd7-40c9-b2cb-7d0f2511d2f9.png)
![switching2](https://user-images.githubusercontent.com/83721477/164190049-b0a01be5-93fa-4980-b86f-30011ac5bf4a.png)
![switching3](https://user-images.githubusercontent.com/83721477/164190360-4c78bb0d-c3d3-4b89-a0b4-55a8b31e98a6.png)
![switching4](https://user-images.githubusercontent.com/83721477/164190865-5fc2d08a-4160-46a1-990d-08abf805caef.png)
![switching5](https://user-images.githubusercontent.com/83721477/164191030-f96191e8-d04c-4004-9f38-9c16d5593dd9.png)

### Apprentissage MAC (Mac learning)
* Pour commuter efficacement les trames entre les ports LAN, le commutateur gère une table d'adresses appelée table MAC.
* Lorsque le commutateur reçoit une trame, il associe l'adresse MAC (Media Access Control) du périphérique réseau émetteur au port LAN sur lequel elle a été reçue.
* L'apprentissage des adresses MAC est activé sur tous les VLAN par défaut
* Le commutateur construit dynamiquement la table d'adresses en utilisant l'adresse source MAC des trames reçues.
* Lorsque le commutateur reçoit une trame pour une adresse de destination MAC non répertoriée dans sa table d'adresses, il diffuse la trame vers tous les ports LAN du même VLAN, à l'exception du port qui a reçu la trame.
* Lorsque la station de destination répond, le commutateur ajoute son adresse source MAC et son ID de port pertinents à la table d'adresses.
* Le commutateur transmet ensuite les trames suivantes à un seul port LAN sans inonder tous les ports LAN.
* Vous pouvez également saisir une adresse MAC, appelée adresse MAC statique, dans le tableau.
* Ces entrées MAC statiques sont conservées lors d'un redémarrage du commutateur.
### Vieillissement MAC (MAC aging)
* Vous pouvez configurer la durée pendant laquelle une entrée (l'adresse MAC source du paquet et le port entrant par le paquet) reste dans la table MAC.
* Vous pouvez également configurer le temps de vieillissement MAC en mode de configuration d'interface ou en mode de configuration VLAN.
* Le temps de vieillissement MAC spécifie le temps avant qu'une entrée expire et soit supprimée de la table d'adresses MAC.
* La plage est de 0 à 1000000 ; la valeur par défaut est de 300 secondes.
* La saisie de la valeur 0 désactive le vieillissement MAC.
* Si aucun VLAN n'est spécifié, la spécification de vieillissement s'applique à tous les VLAN.
### Commutation de trame (Frame switching)
* Les commutateurs LAN sont caractérisés par la méthode de transfert qu'ils prennent en charge, telle qu'un commutateur a store-and-forward, un cut-through ou un commutateur fragment-free.
* Les commutateurs de store-and-forward stockent la totalité de la trame dans la mémoire interne et vérifient la présence d'erreurs dans la trame avant de la transmettre à sa destination.
* Le fonctionnement du commutateur store-and-forward garantit un niveau élevé de trafic réseau sans erreur, car les trames de données erronées sont rejetées plutôt que transmises sur le réseau
* Avec la commutation cut-through, le commutateur LAN copie dans sa mémoire uniquement l'adresse MAC de destination, qui se trouve dans les 6 premiers octets de la trame suivant le préambule.
* Le commutateur recherche l'adresse MAC de destination dans sa table de commutation, détermine le port d'interface sortant et transmet la trame à sa destination via le port de commutateur désigné.
* Un commutateur cut-through réduit le délai car le commutateur commence à transmettre la trame dès qu'il lit l'adresse MAC de destination et détermine le port de commutateur sortant
* La commutation fragment-free fonctionne comme la commutation directe à l'exception qu'un commutateur en mode sans fragment stocke les 64 premiers octets de la trame avant le transfert.
* La commutation fragment-free peut être considérée comme un compromis entre la commutation store-and-forward et la commutation cut-through.
* La raison pour laquelle la commutation sans fragment ne stocke que les 64 premiers octets de la trame est que la plupart des erreurs de réseau et des collisions se produisent pendant les 64 premiers octets d'une trame
### Inondation de trame (Frame flooding)
* Les commutateurs déterminent sur quel port une trame doit être envoyée pour atteindre sa destination
* Si l'adresse est connue, la trame est transmise uniquement sur ce port
* Si l'adresse MAC de la couche 2 est inconnue, la trame est inondée vers tous les ports sauf celui d'où elle provient
### Tableau des adresses MAC
* Une table d'adresses MAC est composée des colonnes suivantes :
  * VLAN
  * Adresse Mac
  * Type (dynamique ou statique)
  * Ports
* Les entrées statiques persisteront lors d'un redémarrage. Les entrées dynamiques ne le seront pas.

