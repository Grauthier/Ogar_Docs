# Protocol Ogar

## Messages Serveurs

### Ajouter une Cellule

#### Paquet

| 1 Octet   | 4 Octets |
| :-------: |:--------:|
| 32        | Id       |

### Supprimer toutes les Cellules

#### Paquet

| 1 Octet   |
| :-------: |
| 18 ou 20 *|

Cela dépend de la version du protocol, 20 si la version du protocol utilisée est
5, 18 sinon.

### Dessiner une ligne

#### Paquet

| 1 Octet   | 2 Octet   | 2 Octet   |
| :-------: | :-------: | :-------: |
| 21        | X         | Y         |

### Messages Clients
