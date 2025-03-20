
# 💪 Progress Pulse - Suivi de séance de musculation - Backend

**Progress Pulse** est une application mobile qui permet de créer ses séances de musculation et de suivre sa progression. C'est un projet de fin de formation **fait en équipe de 3 sur une durée de 2 semaine.**

 L'application inclut des fonctionnalités avancées comme : l'**authentification**, la **création de séance avec objectifs**, le **suivi de séance**, le **temps de repos intégré**, l'**historique des performances** et le **suivi de poids.**

## 🚀 Démo en ligne
🔗 Application déployée : [expo.dev/preview](https://expo.dev/preview/update?message=Stable%20Version&updateRuntimeVersion=1.0.0&createdAt=2025-03-20T15%3A18%3A36.741Z&slug=exp&projectId=073b9ab9-b0d3-452b-8356-4ca49a271182&group=30af1b4d-2424-4643-8852-07171c3f5399) (Téléchargez l'application Expo Go sur votre téléphone et scannez le code QR)\
📹 Vidéo démo : [voir la vidéo démo](https://www.youtube.com/watch?v=Osh-E0SRI3U)\
🛠️ Repo Backend : [Accéder au repo backend](https://github.com/ThomasLebel/ProgressPulse-Backend)

## 📱 Installation & Test
📲 Téléchargez l’application **Expo Go** sur votre téléphone :  
* [iOS - App Store](https://apps.apple.com/app/expo-go/id982107779)  
* [Android - Google Play](https://play.google.com/store/apps/details?id=host.exp.exponent&hl=fr&gl=US)

📸 Une fois Expo Go installé, scannez ce QR code avec votre appareil photo, vous serez redirigé vers Expo Go et l'application se lancera automatiquement :


![QR code progress pulse](https://github.com/user-attachments/assets/eb01de40-3c8e-43e9-82fa-b209862ac629)


## 🧱 Stack technique

| Frontend  | Backend | Base de données | Autres services |
| -------- |-------| ---------------| ---------------|
|React Native|Node.js|MongoDB / Mongoose | Nodemailer (Envoi d'email)|
|Expo|Express.js|| Expo (Déploiement frontend)|
||||Vercel (Déploiement Backend)|


## ⚙️ Fonctionnalités techniques

### API & Base de données
- **Express.js** : API REST pour gérer les utilisateurs, inscriptions, emails, etc.
- **MongoDB + Mongoose** : base de données NoSQL avec schémas, validations et requêtes optimisées.

### Authentification & Sécurité
- **Hash des mots de passe** avec `bcrypt` pour sécuriser les données sensibles.
- **Token d’identification** généré via `uid2` pour authentifier les utilisateurs.
- **Cookies sécurisés** gérés avec `cookie-parser`.
- **CORS** configuré avec `cors` pour contrôler les accès au serveur.
- **Variables d’environnement** via `dotenv` pour protéger les données sensibles (API keys, config).

### Emails & Notifications
- **Envoi d’emails** via `nodemailer` (ex : système de mot de passe oublié).

### Développement & Tests
- **Logs HTTP** avec `morgan` pour surveiller les requêtes entrantes.
- **Tests automatisés** avec `jest` + `supertest` pour valider les routes et les fonctionnalités.
- **Rechargement auto en développement** via `nodemon`.

## ⚡ API Endpoints

### 🙋‍♂️ Routes Users
|Méthode|Route|Fonction|
|-------|-----|--------|
|`POST`|`/users/signup`|Création d’un utilisateur : génération d'un token + hachage du mot de passe.|
|`POST`|`/users/signin`|Connexion utilisateur :comparaison mot de passe avec Bcrypt|
|`PUT`|`/users/changeSound`|Changement du son de fin de timer|
|`PUT`|`/users/changeEmail`|Changement d’email|
|`PUT`|`/users/changePassword`|Changement de mot de passe|
|`PUT`|`/users/changeUsername`|Changement du nom d’utilisateur |
|`POST`|`/users/addWeight`|Ajout d’un poids dans l’historique|
|`POST`|`/users/weightTarget`|Définition d’un objectif de poids |
|`POST`|`/users/forgotPassword`|Demande de réinitialisation du mot de passe|
|`POST`|`/users/verifyResetToken`|Vérifie le token de réinitialisation|
|`POST`|`/users/changeForgottenPassword`|Changement de mot de passe après réinitialisation|
---
### 🏋️‍♂️ Routes UsersWorkouts
|Méthode|Route|Fonction|
|-------|-----|--------|
|`POST`|`/usersWorkouts/addWorkout`|Ajoute une séance personnalisée|
|`GET`|`/usersWorkouts/:userToken`|Récupère toutes les séances de l’utilisateur |
|`DELETE`|`/usersWorkouts/deleteWorkout/:workoutID`|Supprime une séance|
|`DELETE`|`/usersWorkouts/deleteExercise`|Supprime un exercice dans une séance|
|`POST`|`/usersWorkouts/addExercise`|Ajoute un exercice dans une séance|
|`PUT`|`/usersWorkouts/updateSets`|Modifie les objectifs d’un exercice|
|`PUT`|`/usersWorkouts/updateName`|Change le nom d’une séance|

### 📊 Routes Histories
|Méthode|Route|Fonction|
|-------|-----|--------|
|`POST`|`/histories/addWorkout`|Ajouter une séance dans l'historique avec les performances effectuées|
|`GET`|`/histories/:userToken`|Récupère l'historique des séances d'un utilisateur|

### 📚 Routes Workouts
|Méthode|Route|Fonction|
|-------|-----|--------|
|`GET`|`/workouts/`|Récupère toutes les séances prédéfinies|
|`GET`|`/workouts/:byDifficulty`|Récupère les séances selon un niveau|
|`GET`|`/workouts/:byName`|Récupère les séances selon un nom de séance|

### 🎯 Routes Exercises
|Méthode|Route|Fonction|
|-------|-----|--------|
|`GET`|`/exercises/`|Récupère l'ensemble des exercices|
|`GET`|`/exercises/:muscleGroup`|Récupère l'ensemble des exercices correspondant à un groupe musculaire|



## 👨‍💻 Auteurs
[Pierre Gleize](https://github.com/pierreGleize)\
[Alexandre Lassaigne](https://github.com/AlexandreLass)\
[Thomas Lebel](https://github.com/ThomasLebel)

🔗 [Linkedin](https://www.linkedin.com/in/thomas-lebel-6047ba129/)\
📫Contact : thomas.lebel38@gmail.com


