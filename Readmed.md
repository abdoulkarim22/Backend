<!-- pour les installations  -->

npm init -y 

npm install express

npm i mongoose 

<!-- pour les enregistrement auto  -->

npm i nodemon 

<!-- Dossier pour connect mongodb -->

configdb.js





<!-- // Importer les modules nécessaires -->
const express = require('express');
const app = express();

<!-- // Définir le port -->
const PORT =  3000;

<!-- // Définir une route simple -->
app.get('/', (req, res) => {
  res.send('Bienvenue sur mon serveur Node.js avec Express!');
});

<!-- // Démarrer le serveur -->
app.listen(PORT, () => {
  console.log(`Le serveur fonctionne sur http://localhost:${PORT}`);
});



1. Node.js Development
Node.js Extension Pack : Collection d'extensions pour le développement Node.js, y compris des fonctionnalités pour Express et MongoDB.
ESLint : Permet de détecter et corriger les erreurs de style et de syntaxe dans le code JavaScript.
Prettier - Code formatter : Un formatteur de code pour garder le code propre et organisé.
2. Express.js
REST Client : Permet de faire des requêtes HTTP directement depuis VSCode, pratique pour tester vos API Express.
npm Intellisense : Fournit de l’autocomplétion pour les modules npm dans votre projet Node.js.
Path Intellisense : Facilite l'autocomplétion des chemins dans vos fichiers JavaScript/Node.js.
3. MongoDB
MongoDB for VSCode : Une extension officielle par MongoDB pour interagir avec les bases de données MongoDB directement dans VSCode.
Mongoose Snippets : Fournit des snippets pour accélérer le développement avec Mongoose, un ORM pour MongoDB.








1. Installation de MongoDB Atlas :
MongoDB Atlas est un service de base de données cloud.

Étapes :
Créer un compte MongoDB Atlas :

Va sur MongoDB Atlas et crée un compte gratuit.
Crée un Nouveau Projet et ensuite un Nouveau Cluster. Choisis une région proche de toi et une version MongoDB.
Configurer les paramètres réseau :

Dans la section "Network Access", ajoute ton IP publique pour autoriser les connexions à ton cluster.
Tu peux aussi autoriser les accès à toutes les IPs avec l'option "Allow Access From Anywhere", mais c'est moins sécurisé.
Ajouter un utilisateur à la base de données :

Dans la section "Database Access", crée un utilisateur avec un nom d'utilisateur et un mot de passe qui aura accès au cluster.
Obtenir l'URI de connexion :

Une fois le cluster créé, clique sur "Connect", puis "Connect using MongoDB Compass".
Copie l'URI fourni, il ressemble à ceci :
php
Copier le code
mongodb+srv://<username>:<password>@cluster0.mongodb.net/<dbname>?retryWrites=true&w=majority
2. Installation de MongoDB Compass :
MongoDB Compass est un outil graphique pour interagir avec MongoDB.

Étapes :
Télécharge MongoDB Compass depuis le site officiel : MongoDB Compass.
Installe l'application en suivant les instructions fournies pour ton système d'exploitation.
3. Connexion à MongoDB avec MongoDB Compass :
Ouvre MongoDB Compass.
Colle l'URI de connexion que tu as obtenu dans MongoDB Atlas.
Remplace <username>, <password>, et <dbname> avec les valeurs appropriées.
Clique sur "Connect" pour accéder à ta base de données dans MongoDB Atlas.
Fichier de configuration pour le serveur :
Crée un fichier server.js ou db.js pour gérer la connexion à MongoDB dans ton projet.

javascript
Copier le code
const mongoose = require('mongoose');

const connectDB = async () => {
  try {
    const conn = await mongoose.connect('url', {
    });
    console.log(`MongoDB Connected: ${conn}`);
  } catch (err) {
    console.error(`Error: ${err.message}`);
  }
};

module.exports = connectDB;

Fichier principal pour démarrer le serveur :
Crée un fichier app.js qui appelle la fonction pour se connecter à MongoDB et démarre le serveur.

javascript
Copier le code

const express = require('express');
const connectDB = require('./server'); // Si le fichier est nommé server.js

const app = express();

// Connexion à la base de données
connectDB();

app.get('/', (req, res) => {
  res.send('API is running...');
});

const PORT =  5000;
app.listen(PORT, console.log(`Server running on port ${PORT}`));