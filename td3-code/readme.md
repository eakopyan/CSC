# Schéma 1 : chiffrement simple
Processus et coût d'ajout d'un compte et de vérification d'un mot de passe :

En cas de perte de mot de passe :

Information révélée directement par la BD mots de passe : mdp en clair, clé de déchiffrement

* Coût de cassage d'un mdp isolé : négligeable
* Coût de cassage de la base entière : très faible (quelques ms pour ce TP)

# Schéma 2 : sha
Processus et coût d'ajout d'un compte et de vérification d'un mot de passe :

En cas de perte de mot de passe :

Information révélée directement par la BD mots de passe : mdp en clair

* Coût de cassage d'un mdp isolé : très faible, car attaque ciblée donc pas besoin de tester toutes les combinaisons
* Coût de cassage de la base entière : faible (environ 2 secondes)

# Schéma 3 : SaltedSha
Processus et coût d'ajout d'un compte et de vérification d'un mot de passe :

En cas de perte de mot de passe :

Information révélée directement par la BD mots de passe : mdp en clair, salt ajouté

* Coût de cassage d'un mdp isolé : faible (même principe que sha)
* Coût de cassage de la base entière : moyen (environ 20 secondes)

# Schéma 4 : pbkdf2
Processus et coût d'ajout d'un compte et de vérification d'un mot de passe :

En cas de perte de mot de passe :

Information révélée directement par la BD mots de passe : mdp en clair, salt ajouté et nombre d'itérations

* Coût de cassage d'un mdp isolé : moyen (attaque ciblée mais beaucoup de paramètres à prendre en compte)
* Coût de cassage de la base entière : élevé (environ 2 minutes)
