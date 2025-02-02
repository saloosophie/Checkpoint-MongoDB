Projet MongoDB : Manipulation des opérations CRUD
Ce projet consiste à manipuler les opérations CRUD (Create, Read, Update, Delete) dans MongoDB en utilisant une base de données appelée contact et une collection nommée contactlist.

Objectif

L'objectif de ce projet est de :

Créer une base de données et une collection.

Insérer des documents dans la collection.

Effectuer des requêtes pour lire, mettre à jour et supprimer des documents.

Appliquer des filtres pour afficher des données spécifiques.
.............................................................................................................................................

Étapes du projet

1. Créer la base de données et la collection
Utilisez la commande suivante pour créer une base de données contact et une collection contactlist :
.
.
use contact
db.createCollection("contactlist")
.
2. Insérer des documents dans la collection
Insérez les documents suivants dans la collection contactlist :
.
.
db.contactlist.insertMany([
    { "Nom de famille": "Ben", "Prénom": "Moris", "Email": "ben@gmail.com", "age": 26 },
    { "Nom": "Kefi", "Prénom": "Seif", "Courriel": "kefi@gmail.com", "âge": 15 },
    { "Nom": "Emilie", "Prénom": "brouge", "Courriel": "emilie.b@gmail.com", "âge": 40 },
    { "Nom": "Alex", "Prénom": "brown", "âge": 4 },
    { "Nom": "Denzel", "Prénom": "Washington", "âge": 3 }
])
.
3. Afficher toute la liste des contacts
Utilisez la commande suivante pour afficher tous les documents de la collection :
.
.
db.contactlist.find().pretty()
.
4. Afficher les informations d'un contact par son ID
Remplacez ObjectId("...") par l'ID du document que vous souhaitez afficher :
.
.
db.contactlist.find({ _id: ObjectId("...") }).pretty()
.
5. Afficher les contacts ayant un âge > 18
Utilisez la commande suivante pour filtrer les contacts ayant un âge supérieur à 18 ans :
.
.
db.contactlist.find({ "âge": { $gt: 18 } }).pretty()
.
6. Afficher les contacts ayant un âge > 18 et dont le nom contient "ah"
Utilisez la commande suivante pour appliquer un filtre combiné :
.
.
db.contactlist.find({ "âge": { $gt: 18 }, "Nom": { $regex: "ah", $options: "i" } }).pretty()
.
7. Mettre à jour le prénom de "Kefi Seif" en "Kefi Anis"
Utilisez la commande suivante pour mettre à jour le prénom :
.
.
db.contactlist.updateOne(
    { "Prénom": "Seif" },
    { $set: { "Prénom": "Anis" } }
)
.
8. Supprimer les contacts ayant moins de 5 ans
Utilisez la commande suivante pour supprimer les contacts dont l'âge est inférieur à 5 ans :
.
.
db.contactlist.deleteMany({ "âge": { $lt: 5 } })
.
9. Afficher la liste finale des contacts
Après les modifications, affichez à nouveau la liste des contacts :
.
.
db.contactlist.find().pretty()
.
.
.........................................................................................................................................................
   
Résultats attendus

Une base de données contact avec une collection contactlist.

Des documents insérés et manipulés à l'aide des opérations CRUD.

Des captures d'écran montrant les étapes et les résultats des requêtes.
............................................................................................................................................................

Comment exécuter ce projet

Assurez-vous d'avoir MongoDB installé et démarré sur votre machine.

Ouvrez un terminal ou un shell MongoDB.

Suivez les étapes décrites dans ce fichier README.

Sauvegardez les résultats sous forme de captures d'écran.

Salem HAMIDATOU
