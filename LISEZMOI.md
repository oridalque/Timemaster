# Gardien du temps – installation dans Teams

## 1. Héberger les 2 pages web (dossier `site/`)
Teams affiche une page web hébergée en HTTPS. Solution gratuite : GitHub Pages.
1. Créez un dépôt GitHub public `gardien-du-temps` et déposez-y **les 4 fichiers** du dossier `site/` : `index.html`, `config.html`, `gdt-live.js`, `MicrosoftTeams.min.js`.
2. Settings > Pages > Branch `main` / root > Save.
3. L'URL obtenue ressemble à `https://VOTRE-COMPTE.github.io/gardien-du-temps/`.
(Alternatives : Azure Static Web Apps, ou tout serveur web HTTPS de l'entreprise.)

## 2. Adapter le manifeste (dossier `teams/`)
Dans `manifest.json`, remplacez partout `VOTRE-DOMAINE.github.io/gardien-du-temps`
par votre URL (sans `https://`), et `validDomains` par le seul domaine (ex. `votre-compte.github.io`).
Puis zippez **le contenu** du dossier (manifest.json, color.png, outline.png à la racine du zip, sans sous-dossier).

## 3. Installer
- Test perso : Teams > Applications > Gérer vos applications > Charger une application > « Charger une application personnalisée ».
- Pour tout le cabinet : Centre d'administration Teams > Applications Teams > Gérer les applications > Charger une nouvelle application.
  Vérifiez que les applications personnalisées sont autorisées dans la stratégie de configuration.

## 4. Utiliser en réunion (temps réel)
1. Dans la réunion : **+ Applications** > Gardien du temps > Enregistrer. L'appli devient disponible pour tous les participants.
2. Ouvrez-la dans le **panneau latéral** : la pastille « Synchronisé avec la réunion » confirme la connexion. Vos réglages (phases) sont envoyés à la réunion.
3. Pour que les participants voient le timer, deux façons, toutes deux synchronisées en direct :
   - **Pendant que vous présentez des slides** : chaque participant ouvre Gardien du temps dans son propre panneau latéral (icône de l'appli dans la barre de réunion). Le timer reste à côté de votre partage d'écran.
   - **Sans partage d'écran** : bouton « Partager sur l'écran de réunion » ; le timer s'affiche en grand pour tous (cela remplace le partage d'écran).
4. Démarrer, pause, phase suivante, réinitialiser, modifier les phases : tout est répercuté chez tous en moins d'une seconde.
   Seuls l'**organisateur et les présentateurs** peuvent piloter ; les participants suivent.

## 5. Hors réunion
- **Appli personnelle** : icône dans la barre latérale de Teams (timer local, non partagé). Clic droit > « Ouvrir dans une nouvelle fenêtre » pour la redimensionner.
- **Logo et fond** : Paramétrer > Apparence. Ils restent sur votre poste et ne sont pas transmis aux participants.
- Raccourcis : Espace (démarrer/pause), N (phase suivante), R (réinitialiser), P (paramétrer).

## Bon à savoir
- La synchronisation utilise Microsoft Live Share, inclus dans Teams : aucun serveur ni abonnement supplémentaire.
- Elle ne fonctionne que dans une réunion Teams planifiée ou instantanée (pas dans une conversation ou un canal hors réunion).
- Si la pastille indique « Synchronisation indisponible », le timer fonctionne en local : vérifiez que le package installé est bien la version 1.1.0.
