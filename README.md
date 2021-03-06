# MongoDB

## Contexte

Nous sommes dans un contexte où une chaîne de restaurants souhaite récupérer des données client dans le but de capitaliser sur un flux de personnes grandissant. L'utilisation d'un SGBD tel que MongoDB est pertinent dans ce cas, étant donné que nous voulons ordonner toutes les données client et les réutiliser dans un contexte de Big Data qu'on peut gérer en temps réel.
MongoDB a pour avantage sa structure en NOSQL différente de celles en SQL. En effet, celle-ci est composée de 3 éléments :
  -La database
  -La collection
  -Le document
La database est ce qui contient toutes les collections, qui elles contiennent tous les documents. Les documents contiennent eux tous les éléments et données client.

MongoDB est un SGBD populaire, et possède donc une grande communauté active, ce qui permet donc d'avoir accès à de nombreuses documentations selon la technologie utilisée.

Dans MongoDB, on peut stocker différents types de données :
  -Les documents, qui contiennent toutes les données en lignes
  -Les graphes, qui stockent les informations de réseaux de données
  -Les clés/valeurs, qui stocke les données avec une clé d'attribut et sa valeur associée
  -Les données orientées colonnes, qui sortent les mêmes données que les documents mais sous forme de colonnes
  
Le domaine du commerce génère énormément de données. Il utilise donc les SGBD pour les gérer. Les entreprises utilisent donc des SGBD tels que MySQL, Oracle, ou encore MongoDB si NOSQL. Cela leur permet de réaliser des requêtes et de ressortir les données nécessaires rapidement, ainsi que de pouvoir les utiliser dans un contexte géospatial.

Ce type de données est intéressant dans notre contexte. En effet, nous pouvons ressortir les coordonnées en latitude et longitude des différents restaurants afin de pouvoir les localiser sur une carte. Ainsi, nous pouvons déterminer par exemple la distance entre le domicile d'un client et le restaurant, et une possibilité d'avoir toutes les informations de contact directement sur la carte.
  
## Partie technique

Nous comptons réaliser sur MongoDB 4 collections :
  -Les restaurants, qui contiendront donc le nom et l'adresse, elle-même composée de son libellé, de sa ville et du code postal
  -Les produits, qui contiendront le nom, le prix et la réduction sur les produits
  -Les clients, qui renseigneront leur nom, leur prénom, leur date de naissance, ainsi que leurs coordonnées (adresse, mail, téléphone) et leur mot de passe
  -Les commandes, qui auront donc la liste des commandes avec comme informations le nom du restaurant, le nom et prénom du client, la date de la commande ainsi que le produit et sa réduction.
  
![MicrosoftTeams-image](https://user-images.githubusercontent.com/65296828/148961709-7a271d90-b25f-436d-9a10-479ac2b1381a.png)

### Requêtes de base

#### Insert

La commande insert est utilisée dans le but d'ajouter un ou plusieurs documents dans une collection (dans le cas d'une insertion multiple, on n'utilise pas InsertOne mais InsertMany)

![image](https://user-images.githubusercontent.com/65296828/149342659-9e52ae1c-e982-47e4-8323-a1265ae49eca.png)

#### Delete

On utilise la commande delete pour supprimer un ou plusieurs documents d'une collection (dans le cas d'une suppression multiple, on n'utilise pas DeleteOne mais DeleteMany)

![image](https://user-images.githubusercontent.com/65296828/149343539-66f7d3de-ef17-440f-b0ff-33504c94979d.png)

#### Find

Le find est utilisé pour ressortir des données de documents.

![image](https://user-images.githubusercontent.com/65296828/149344290-ce6fd0b4-ff24-49c3-ba26-07ddf6134751.png)


#### Pretty

On utilise pretty pour sortir les données d'un find de manière plus jolie.

![image](https://user-images.githubusercontent.com/65296828/149356003-9e0ac58d-6b8c-42ed-8282-b224a93ddddd.png)


#### Explain

La fonction explain permet de savoir des informations sur le plan de requête. Tout le processus de ce plan sort sous la forme d'un document détaillé.

### Requêtes géospatiales

Lorsqu'on souhaite retrouver des éléments dans un contexte géospatial, on peut utiliser des requêtes géospatiales. Celles-ci servent à sortir toutes les données d'une base de données qui peuvent être proches d'un point donné sur une carte, un polygone, etc...
Ainsi, on peut savoir quels sont par exemple les magasins les plus proches de notre location, ou d'un autre lieu en particulier, ou encore les cinémas.
On utilise donc des requêtes pour les données GeoJson, qui tournent à partir des mots-clés $near et $within. On utilise le premier pour déterminer les données proches d'un point précis, et le second pour déterminer toutes les données présentes dans une zone donnée.

![image](https://user-images.githubusercontent.com/65296828/149361775-c15b18dc-339d-4281-8490-80664ce62982.png)
