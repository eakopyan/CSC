# Schéma 1 : chiffrement simple AES
Processus et coût d'ajout d'un compte et de vérification d'un mot de passe : négligeable

En cas de perte de mot de passe : possible de lui renvoyer car crypto réversible, mais pas sécurisé

Information révélée directement par la BD mots de passe : longueur mdp, mdp identiques (même chiffré)

* Coût de cassage d'un mdp isolé : négligeable
* Coût de cassage de la base entière : très faible (quelques ms pour ce TP)

AES est devenu complètement obsolète.


# Schéma 2 : sha256
Processus et coût d'ajout d'un compte et de vérification d'un mot de passe : négligeable

En cas de perte de mot de passe : réinitialisation du mdp

Information révélée directement par la BD mots de passe : mdp identiques

* Coût de cassage d'un mdp isolé : x(grand) <=> le coût devient élevé quand l'espace est restreint. Coût négligeable via Google (indexation)
* Coût de cassage de la base entière : plus ou moins pareil (environ 2 secondes)


# Schéma 3 : Salted Hash
Processus et coût d'ajout d'un compte et de vérification d'un mot de passe : négligeable

En cas de perte de mot de passe : réinitialisation du mdp

Information révélée directement par la BD mots de passe : N/A (chiffrés différents pour mdp identiques)

* Coût de cassage d'un mdp isolé : x(grand), même principe que sha256 sans Google
* Coût de cassage de la base entière : nx(grand) (environ 20 secondes)


# Schéma 4 : pbkdf2
Processus et coût d'ajout d'un compte et de vérification d'un mot de passe : un peu moins négligeable

En cas de perte de mot de passe : réinitialisation du mdp

Information révélée directement par la BD mots de passe : N/A

* Coût de cassage d'un mdp isolé : cx(grand) (itérations)
* Coût de cassage de la base entière : ncx(grand) (environ 2 minutes)
