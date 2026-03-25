
API Blog — Projet INF222

Ce projet est une API REST construite avec Node.js, Express et SQLite pour gerer les articles d'un blog.

### Fonctionnalites

Le projet est organisé en plusieurs parties distinctes :

* Le dossier **api-blog-inf222/** regroupe toute la logique backend basée sur Express. On y trouve la gestion des articles (création, lecture, modification, suppression), un système de recherche, la documentation Swagger ainsi qu’une base de données SQLite.
* Validation des donnees : Utilisation d'un middleware pour verifier que le titre, l'auteur et le contenu sont presents
* Base de donnees : Stockage permanent dans un fichier SQLite.
* Recherche :  Possibilite de filtrer kes articles parmots-cles.


 * Installer les dépendances :
   npm install

 * Lancer le serveur :
   node server.js

   Le serveur sera accessible sur : http://localhost:3000
   
📬 Routes de l'API
| Méthode | Route | Description |
|---|---|---|
| GET | /api/articles | Liste tous les articles |
| GET | /api/articles/:id | Affiche un article spécifique |
| POST | /api/articles | Crée un nouvel article |
| PUT | /api/articles/:id | Modifie un article existant |
| DELETE | /api/articles/:id | Supprime un article |


### Démarrage en local

Pour exécuter le projet sans Docker :

```bash id="k2d83j"
cd Blog-api
npm install
npm start
```

Le serveur est accessible par défaut sur le port **4000**, sauf configuration différente via un fichier `.env`.

---

### Accès aux différentes routes

Une fois l’application lancée, plusieurs points d’accès sont disponibles :

* La racine (`/`) redirige automatiquement vers la documentation Swagger.
* La route `/ui` permet d’accéder à l’interface utilisateur.
* La page `/Frontend/index.html` correspond à l’interface complète du blog.
* `/api-docs` donne accès à Swagger pour explorer et tester les endpoints.
* `/api/articles` retourne directement les données au format JSON.

⚠️ Il est conseillé d’utiliser `localhost` ou `127.0.0.1` dans le navigateur, car l’adresse `0.0.0.0` peut ne pas être acceptée.

---

### Tests avec curl

* Une requête vers `/` entraîne une redirection (code 302). Pour la suivre automatiquement :

  ```bash
  curl -L http://localhost:4000/
  ```
* Pour récupérer directement les données :

  ```bash
  curl http://localhost:4000/api/articles
  ```



### Conclusion

Le projet aboutit à une API opérationnelle, accessible aussi bien en local qu’en ligne. Les fonctionnalités principales (CRUD et recherche) sont documentées via Swagger, et une interface graphique permet de faciliter les tests. Les aspects liés au déploiement et à Docker sont également pris en compte.


