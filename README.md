# SQL avancé

## Different type

* **blob** : binaire
* **varchar** : chaine de caractere
* **int** : entier
* **double** : decimal

## Database language

* DML (data manipulation language) : `select, insert, update, delete`
* DDL (data definition language) : `drop, alter, create, truncate`
* TCL (transaction control language) : `start transaction, commit, rollback`
* DCL (data control language) : `grant, revoke`

## Exemple

**DUMP** = fichier de sauvegarde qu'on garde dans la base de données

```SQL
CREATE TABLE dump_user(
	id int,
	name varchar(255)
);

CREATE TABLE user(
	id int,
	nom varchar(255)
);
```

## Fonction d'agrégats

Les fonctions d'agrégats fonctionne avec un groupe de tuples. Notamment avec un `GROUP BY`.

* **SUM** : fait la somme d'un groupe de valeur
* **COUNT** : compte le nombre de ligne d'un groupe de valeur
* **MAX** : prend la valeur max d'un groupe de valeur
* **MIN** : prend la valuer min d'un groupe de valeur
* **AVG** : fait la moyenne d'un groupe de valeur

## Fonction scalaire

Les fonctions scalaire fonctionne sur une utilisation par colonne. Fonction enclenché côté server.

* **NOW** : prend la date d'aujourd'hui
* **UPPER** : change la case en uppercase
* **LOWER** : change la case en lowercase
* **ROUND** : change l'arrondissement

## Exemple avec fonction

```SQL
SELECT prenom, nom, AVG(age) as moy_age
FROM user
GROUP BY nom, prenom;

SELECT UPPER(prenom) as prenom, nom, age
FROM user;
```

## Connexion à un base de données

* Nom de la base de données
* Nom de la machine (ex: IPv4)
* Identifiants SGBDR (login/passw)
* Port : 0 à 65335, accès avec des protocoles de bases (ex: TCP)

## JDBC (Java Database Connectivity)

C'est une API de connection à une base de données en JAVA

Fonctionnalités : 

* Connection : Endpoint connection 
* Statement : Requete fixe
* Prepared Statement : Requete dynamique
* ResultSet : tableau de resultat d'une requete
