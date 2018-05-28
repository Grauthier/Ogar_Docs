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

| 1 Octet   | 2 Octets  | 2 Octets  |
| :-------: | :-------: | :-------: |
| 21        | X         | Y         |

### Placer les bordures

#### Paquet

| 1 Octet   | 8 Octets  | 8 Octets  | 8 Octets  | 8 Octets  |
| :-------: | :-------: | :-------: | :-------: | :-------: |
| 64        | Left      | Top       | Right     | Bottom    |

### Mettre à jour le tableau des scores

On n'utilisera pas ce paquet.

### Mettre à jour les Cellules

#### Paquet

| 1 Octet   | 2 Octets  || 4 Octets  | 4 Octets  | 8 Octets  | ...  || 4 Octets  | 4 Octets  | 4 Octets  | 2 Octets  | ...  |
| :-------: | :-------: || :-------: | :-------: | :-------: | :--: || :-------: | :-------: | :-------: | :-------: | :--: |
| 16        | DSize     || Id (Eaten)| Id (Eater)| Bottom    | ...  || Id        | X         | Y         | Size      | ...  |

À terminer d'analyser


### Messages Clients
