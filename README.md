 # Facturation
## An app Jean Christian RANU

Afin d'approfondir les notions de bases de données, tables, requêtes SQL et surtout PHP OO nous allons créer une application de facturation pour JC Ranu.
Nous utiliserons l'approche MVC vue en cours pour l'organisation du projet.

## Le projet
Pour un meilleur suivi de projet 
  - Créer un repository pour le projet(Nom du projet débutant par une majuscule
  - Votre repertoire pour le projet contiendra un repertoire Db qui contiendra le script pour la base de donnée facturation  
  - Créer un branche de travail, lorsque vous êtes satisfait du résultat, faites un merge avec la branche master
  - On utilisera la convention camelCase pour la denomination des variables
  - Vous pouvez utiliser Bootstrap et son super CSS lié aux tableaux pour faire votre application.

## Base de données facturation

| personnes      | etage |
| ------------- |
| id_personne     |
| nom_personne       |
| prenom_personne |
| tel_personne |
| email_personne |


| societes      |
| ------------- |
|  id_societe |
| nom_societe |
| adresse_societe |
| tel_societe |
| tva_societe  |


| factures |
| ------------- |
| id_facture |
| numero_facture |
| date_facture |

| type |
| ------------- |
| id_type |
| type |

**Notes**

  - Les numéros de facture peuvent comporter des chiffres et des lettres. (on y stockera les factures clients et fournisseurs)
  - Type : la société peut être un fournisseur ou un client, pas les deux.
  - Concernant les relations entre les tables, il faudra :
  - societes---type
  - societes---factures
  - personnes---factures
  - personnes---societes
  
  Cela signifie qu'il faudra peut-être (surement) rajouter des colonnes à certaines endroits et réfléchir aux liaisons (1:1, 1:m, m:m),...

## L'app pour Ranu

Avec cette base de données, on va faire une petite application (comme un site web) avec les pages suivantes :
- accueil,
- fournisseurs (fournisseur.php),
- clients (client.php),
- factures (facture.php),
- annuaire (annuaire.php),
- details d'une societe (detailsociete.php),
- details d'une facture (detailfacture.php),
- details d'une personne de contact (detailcontact.php)

### page d'accueil
Affichera :
- un message d'accueil pour Jean-Christian Ranu
- la liste des 3 dernières factures, classées par date (chaque facture renvoie avec un lien vers sa page detailfacture)
- la liste des 3 dernières personnes, encodées dans la base de données (chaque personne renvoie avec un lien vers sa page detailcontact)
- la liste des 3 dernières entreprises, encodées dans la base de données (chaque société renvoie à l'aide d'un lien vers sa page detailsociete)
- un lien vers la page fournisseurs
- un lien vers la page clients

### page factures
Affichera la liste des numéros de toutes les factures par date la plus récente vers la date la plus lointaine.

Chaque numéro de facture sera un lien qui, au clic, renverra vers une page detailfacture dont le contenu sera généré en fonction de l'id de la facture sélectionnée.

### page annuaire
Affichera la liste de toutes les personnes de contact de la base de données, par ordre alphabétique.

Le nom de chaque personne sera un lien qui renverra vers une nouvelle page detailcontact dont le contenu sera généré en fonction de l'id de la personne choisie.

BONUS : On appliquera un filtre par société pour mieux trier les personnes de contact

### page fournisseurs
Affichera la liste de toutes les sociétés de type fournisseur. Chaque nom de société renvoie, à l'aide d'un lien, vers sa page detailsociete dédiée.
BONUS : On appliquera un filtre par société pour mieux trier les factures

### page clients
Affichera la liste de toutes les sociétés de type client. Chaque nom de société renvoie, à l'aide d'un lien, vers sa page detailsociete dédiée.
BONUS : On appliquera un filtre par société pour mieux trier les factures

### detailsociete
Affichera les informations suivantes selon la société choisie :
- nom de la société
- adresse de la société
- téléphone de la société
- numéro de TVA de la société
- compte bancaire de la société
- liste des factures liées à la société
- liste des personnes de contact travaillant dans la société

## detailfacture
Affichera les informations suivantes selon la facture choisie :
- numéro
- date
- société liée à la facture
- type de la société liée à la facture (fournisseur ou client)
- personne de contact liée à la facture

### detailcontact
Affichera les informations suivantes selon la personne de contact choisie :
- nom, prénom
- téléphone
- e-mail
- nom de la société où travaille la personne
- adresse de la société
- la liste des factures liées à la personne



Réaliser un petit design sympa pour notre ami Jean-Christian. Rappelez-vous que notre ami est comptable à la COGIP depuis plus de 20 ans !
Pour vous aider voici JP.
![Jean-Christian Ranu de la COGIP](cogip_badge.jpg)
