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
    git commit -m "Missatge..."

Observant canvis registrats:

    git log
    git diff HEAD^


# Links

- [Pro git - llibre online](https://git-scm.com/book/en/v2)
