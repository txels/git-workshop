# Control de Versions?

- Possibilitat de guardar tot l'historial de canvis a un grup d'arxius
- Pots comparar versions en diferents moments
- Pots tornar enrera en el temps

# Tipus de Sistemes:

![Centralitzat](https://homes.cs.washington.edu/~mernst/advice/version-control-fig2.png)


![Descentralitzat](https://homes.cs.washington.edu/~mernst/advice/version-control-fig3.png)


Al sistema descentralizat, tens una còpia completa del repositori (amb tot
l'historial de canvis).

- Pots treballar desconnectat de la xarxa.
- Només necessites connexió per a sincronitzar canvis.

# Operacions bàsiques

- commit: registrar una nova versió (conjunt de canvis)
- push: enviar canvis locals a un servidor remot
- pull: descarregar canvis d'un servidor remot


# git

Avantatges de git

- Descentralitzat
- Molt bona gestió de branques
- Molt eficient


# Utilitzant git - primers passos

Configurar:

    git config --global user.name "John Doe"
    git config --global user.email johndoe@example.com

Necessitarem un repositori. Crear un repo nou:

    git init .

...o clonar un repo existent:

    git clone https://github.com/txels/apitopy.git


# Fent canvis

Si modifiquem arxius localment... què hem canviat?

    git status
    git diff

(diff només ens dirà què ha canviat en arxius que ha estan en control de
versions).

Registrant canvis:

    git add <arxiu[s]>
    git diff --cached
    git commit -m "Missatge..."

Observant canvis registrats:

    git log
    git log --oneline --decorate --graph
    git show HEAD

Cada commit té un identificador únic (SHA-256).


# Parèntesi: què vol dir HEAD?

HEAD és una referència (`ref`) que apunta al darrer commit de la branca actual.
(Veurem més en detall branques després). 
Per ara saber que hi ha una branca per defecte: `master`.

## Refs

Una referència en git és una mena de "punter" a una versió concreta del
repositori. Altres referències que podem fer servir:

- Noms de branques
- IDs de commits
- Etiquetes (tags)
- Referències relatives, p.e.:
  - `HEAD^` és el commit anterior al darrer.
  - Es pot fer servir també `HEAD^^`, `HEAD~2` etc...
  - `master^`

# Desfent canvis

Desfer el darrer commit:

    git reset HEAD^

Es poden moure i esborrar arxius:

    git mv <nom-original> <nom-nou>
    git rm <nom>

...per registrar els canvis, cal fer commit!


# Parèntesi: index o "staging" area

En git, els canvis es registren en dues "fases":

- stage (add, mv, rm...)
- commit: registrar els canvis amb un missatge (git assigna un ID únic)

Veure què hem canviat:

    git diff  # canvis que no estan a l'index, no es commitegen per defecte
    git diff --cached  # canvis que estan a l'index, es commitejaran


![Cicle d'estats](https://git-scm.com/book/en/v2/images/lifecycle.png)


# Compartint canvis amb el món



# Links

- [Pro git - llibre online](https://git-scm.com/book/en/v2)
