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