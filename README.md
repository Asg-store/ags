# AGS CODE STUDIO

Starter complet d'un atelier de création web et mobile en thème sombre.

## Inclus
- Interface responsive en français (ordinateur et téléphone).
- Éditeur HTML avec aperçu en direct.
- Constructeur visuel simple avec blocs ajoutables/supprimables.
- Sauvegarde locale dans le navigateur.
- Export du code en fichier HTML.
- Parcours de préparation Android via Capacitor.
- Serveur facultatif pour assistant IA; la clé API reste côté serveur.

## Prérequis
- Node.js 20 ou plus récent
- npm
- Pour Android : Android Studio et Android SDK

## Démarrer l'application web
À la racine du projet :

```bash
npm install
npm run dev
```

Ouvrir l'adresse locale affichée par Vite.

## Activer l'assistant IA (facultatif)
1. Copier `.env.example` vers `.env` à la racine.
2. Ajouter une clé API valide dans `OPENAI_API_KEY`.
3. Dans un terminal, lancer `cd server && npm install && npm start`.
4. L'interface envoie les demandes à `http://localhost:8787/api/generate`.

Pour un déploiement, configurez une URL serveur HTTPS dans `src/main.jsx` et définissez CORS sur votre domaine précis. Ne publiez jamais la clé API dans le code client.

## Préparer Android
À la racine :

```bash
npm install
npm run build
npx cap add android
npm run android:sync
npm run android:open
```

Dans Android Studio, configurez le SDK, testez sur émulateur ou appareil, puis générez un APK/AAB depuis le menu Build. La compilation Android nécessite un ordinateur avec Android Studio.

## Limites de cette version
- L'éditeur intégré est un éditeur HTML de démarrage, pas encore un IDE professionnel multi-fichiers.
- Le constructeur visuel est une maquette fonctionnelle simple; il n'effectue pas encore une conversion complète de tous les blocs en code.
- La publication d'un site nécessite un hébergement web séparé.
- La génération IA nécessite une clé et un serveur configurés.
- Les sauvegardes sont locales au navigateur; elles ne sont pas synchronisées entre appareils.

## Structure
- `src/` : interface React
- `server/` : API facultative pour l'assistant IA
- `capacitor.config.json` : configuration de l'application Android
