# Smart Biz — MVP e-commerce

Application web de démonstration pour gérer une boutique e-commerce.

## Démarrer en local

Prérequis : Node.js 18 ou plus récent.

```bash
npm install
npm run dev
```

Ouvrir l'URL affichée par Vite (généralement http://localhost:5173).

Pour compiler :
```bash
npm run build
npm run preview
```

## Fonctionnalités disponibles dans cette version

- Tableau de bord et indicateurs de démonstration
- Catalogue produits : ajout, suppression, recherche et catégories
- Boutique client et panier
- Création de commandes de démonstration
- Mise à jour du statut des commandes
- Paramètres de boutique
- Persistance locale dans le navigateur via `localStorage`
- Interface responsive pour mobile et ordinateur

## Important : périmètre de cette livraison

Cette version est un **MVP frontend fonctionnel**, pas encore une plateforme SaaS de production. Les données sont stockées dans le navigateur utilisé et ne sont pas synchronisées entre appareils ou utilisateurs. L'authentification, la base de données serveur, les rôles, les paiements réels, les e-mails, la sécurité et l'hébergement doivent être intégrés avant une mise en production.

## Architecture conseillée pour la version production

- Frontend : React + Vite (ou Next.js)
- API : Node.js / NestJS
- Base de données : PostgreSQL
- Authentification : sessions sécurisées / fournisseur d'identité
- Fichiers produits : stockage objet compatible S3
- Paiements : intégration contractuelle d'un prestataire compatible avec le pays et le compte marchand
- Déploiement : frontend + API + base de données managée

Ne stockez jamais de secrets ou clés privées dans le frontend.
