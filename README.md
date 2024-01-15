# Immo Admin en React
Ce site est le site administration de Immo.

# Installation
Au premier lancement du docker compose, votre conteneur manquera des node_modules.
Pour remédier à cela, il va vous falloir installer les dépendances.

Pour cela, on va utiliser un conteneur éphémère qui aura pour rôle d'installer les dépendances npm puis de s'autodétruire.

```bash
docker run --rm -v $(pwd):/app -w /app node:20-alpine npm install
```

Cette commande crée un conteneur à la même version que notre service `vite` dans le `docker-compose`, à savoir la version `node:20-alpine`.

Il exécute ensuite la commande `npm install` pour installer les dépendances.

Enfin le conteneur se détruit.

Maintenant, vous n'avez plus qu'à lancer la commande

```bash
docker-compose up -d
```

Pour exécuter le conteneur de l'application.

L'application est ensuite disponible à l'adresse 
```http request
http://localhost:3000
```

Ou bien au port que vous avez renseigné dans votre fichier `.env`.