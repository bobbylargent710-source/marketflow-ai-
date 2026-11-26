# MarketFlow AI — MVP

MVP web responsive en français pour génération de contenus marketing.

## Fonctionnalités incluses
- Inscription et connexion par e-mail/mot de passe (hash bcrypt, cookie de session HTTP-only).
- Tableau de bord avec quota de générations.
- Générateur de textes pour Facebook, Instagram, TikTok et WhatsApp.
- Historique des contenus sauvegardés.
- Plans Découverte, Starter, Business et Premium.
- Formulaire de demande de paiement MTN MoMo / Orange Money avec statut `PENDING`.

## Lancer le projet
Prérequis : Node.js 20+, PostgreSQL.

```bash
npm install
cp .env.example .env
# Configurez DATABASE_URL et AUTH_SECRET dans .env
npx prisma generate
npx prisma db push
npm run dev
```
Ouvrir http://localhost:3000.

## Connecter un vrai fournisseur IA
Le MVP accepte un endpoint compatible avec une API de chat qui renvoie `choices[0].message.content`.
Configurez `AI_API_URL`, `AI_API_KEY` et `AI_MODEL`. Sans ces valeurs, un texte de démonstration est renvoyé.

## Paiements MTN MoMo et Orange Money
Le formulaire crée uniquement une demande `PENDING`. Aucun argent n'est encaissé et aucun forfait payant n'est activé automatiquement. Pour passer en production :
1. Contracter avec MTN MoMo, Orange Money ou un agrégateur autorisé disponible au Cameroun.
2. Implémenter l'API d'initiation correspondant à la documentation et aux identifiants du marchand.
3. Ajouter un webhook serveur avec validation de signature et vérification du statut auprès du prestataire.
4. Activer le forfait uniquement après confirmation serveur fiable du paiement.
5. Tester les paiements en sandbox avant le lancement.

## À compléter avant commercialisation
- Limitation de débit, protection CSRF adaptée, validation renforcée et journalisation.
- Vérification e-mail, réinitialisation de mot de passe, politique de confidentialité et CGU.
- Intégration réelle IA, mesure des coûts et filtres anti-abus.
- Paiement réel, webhooks signés et gestion des renouvellements/annulations.
- Tests automatisés, sauvegardes, monitoring, audit de sécurité et déploiement HTTPS.
- Interface d'administration, factures/reçus et gestion complète des abonnements.

Ce dépôt est un socle MVP de développement, pas un service prêt à encaisser des paiements en production.
