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

`*` Cela dépend de la version du protocol, 20 si la version du protocol utilisée est
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
| 1 Octet   | 2 Octets  | ? Octets        | ? Octets | 4 Octet  | 2 ou 4 Octets* | ? x 4 Octets |
| :-------: | :-------: | :-------------: | :------: | :------: | :------------: | :----------: |
| 16        | DeSize    | Cellules Mortes | Cellules | 0        | RmSize         | Id           |

`*` Cela dépend de la version du protocol : 4 Octets pour la version 5 et 2 pour les autres.

##### Cellules Mortes

| 4 Octets  | 4 Octets  |
| :-------: | :-------: |
| Id (Eaten)| Id (Eater)|

##### Cellules

###### Protocole Version 5

| 4 Octets  | 4 Octets  | 4 Octets  | 2 Octets  | 1 Octet   | 1 Octet   | 1 Octet   | 1 Octet   | ? Octets      | 1 Octet   |
| :-------: | :-------: | :-------: | :-------: | :-------: | :-------: | :-------: | :-------: | :-----------: | :-------: |
| Id        | X         | Y         | Size      | R         | G         | B         | Flags     | Name (Unicode)| 0         |

###### Protocole Version ~

| 4 Octets  | 4 Octets  | 4 Octets  | 2 Octets  | 1 Octet   | 1 Octet   | 1 Octet   | 1 Octet   | ? Octets   | 1 Octet   |
| :-------: | :-------: | :-------: | :-------: | :-------: | :-------: | :-------: | :-------: | :--------: | :-------: |
| Id        | X         | Y         | Size      | R         | G         | B         | Flags     | Name (UTF8)| 0         |


### Mettre à jour la Position

#### Paquet

| 1 Octet   | 4 Octets  | 4 Octets  | 4 Octets  |
| :-------: | :-------: | :-------: | :-------: |
| 17        | X         | Y         | Size      |


### Messages Clients

...
