# Communication Mastery — PWA

Application web progressive installable (PWA) pour un parcours de communication de 12 semaines.

## Contenu
- 12 semaines et 60 leçons (5 leçons par semaine), chacune avec concept + exercice.
- Progression persistée dans le stockage local du navigateur.
- Journal personnel, export/import de sauvegarde JSON.
- Ressources externes avec liens.
- Coach IA : mode hors ligne avec retours guidés heuristiques; connexion facultative à un endpoint compatible OpenAI Chat Completions.
- Cache de l'application via Service Worker pour accès hors ligne à l'interface et au programme.

## Lancer en local
Les PWA/service workers ont besoin de localhost ou HTTPS. Dans le dossier:
```bash
python -m http.server 8000
```
Puis ouvrir `http://localhost:8000`.

## Installer sur Android
1. Déployer les fichiers sur un hébergement HTTPS (par ex. GitHub Pages, Netlify, Cloudflare Pages).
2. Ouvrir l'URL dans Chrome Android.
3. Menu ⋮ → Installer l'application / Ajouter à l'écran d'accueil.

## Coach IA
Dans Réglages, fournir:
- endpoint API compatible OpenAI Chat Completions (ex. `https://api.openai.com/v1/chat/completions`)
- nom de modèle disponible chez ton fournisseur
- clé API

La clé est conservée dans localStorage sur l'appareil et envoyée directement au endpoint depuis le navigateur. Ne pas utiliser cette configuration sur un appareil partagé ou pour une application distribuée à d'autres utilisateurs. Pour une version publique, intégrer le fournisseur IA derrière un backend sécurisé, sans exposer de clé dans le navigateur. Certains fournisseurs exigent une configuration CORS compatible.

## Notes
- La PWA est installable, mais un fichier de code seul ne crée pas un lien d'installation public. Il faut l'héberger sur HTTPS.
- Le cache hors ligne garde l'interface et les leçons. L'IA nécessite une connexion internet.
- Les liens des ressources mènent vers des sites externes, susceptibles de modifier leur contenu.
