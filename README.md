# المصحف الشريف - Application Mobile Android (APK)

Application mobile moderne, fluide et complète du Saint Coran, basée sur Capacitor et optimisée pour Android.

---

## 🚀 Améliorations et Nouvelles Fonctionnalités Implémentées

### 1. Navigation et Fermeture Intuitives
- **Gestion intelligente du bouton « Retour » d'Android** :
  - **Fermeture des panneaux ouverts** : Si une feuille inférieure (*Tafsir*, *Tilaawa*) ou une boîte de dialogue (*Paramètres*, *Horaires de prière*, *Douas*, *Révision*) est ouverte, le bouton Retour ferme uniquement ce panneau sans quitter l'écran de lecture.
  - **Retour de lecture** : Si vous êtes en mode lecture d'une sourate, le bouton Retour revient au sommaire des sourates.
  - **Réinitialisation de la recherche et des onglets** : Efface le champ de recherche ou revient au premier onglet (Sourates).
  - **Protection contre la fermeture accidentelle** : Sur l'écran d'accueil, l'application affiche un message toast (*« اضغط مرة أخرى للخروج من التطبيق »*) et ne se ferme que si vous appuyez une seconde fois dans les 2 secondes.
- **Fermeture par clic sur l'arrière-plan (Backdrop)** : Un simple appui à l'extérieur d'une fenêtre modale ou d'une feuille inférieure la referme instantanément.
- **Glissement vers le bas (Swipe-down to dismiss)** : Les feuilles de Tafsir et de lecture audio disposent d'une poignée visuelle et se ferment d'un glissement fluide du doigt vers le bas.
- **Boutons de fermeture accessibles** : Zones de contact élargies (minimum 44×44 px) et contraste renforcé.

### 2. Fluidité et Ergonomie Mobile
- **Réactivité tactile instantanée** : Suppression du délai de 300 ms au toucher (`touch-action: manipulation`) et retour visuel tactile dynamique (`:active { transform: scale(0.96); }`).
- **Défilement et transitions à 60/120 FPS** : Accélération matérielle GPU (`translate3d`, `will-change: transform`), défilement avec inertie native et confinement des débordements (`overscroll-behavior-y: contain`).
- **Adaptation au clavier virtuel** : Prise en charge de `interactive-widget=resizes-content` et défilement automatique des champs de saisie (douas, notes, recherche) lors de l'ouverture du clavier Android.
- **Prise en compte des encoches (Notch / Safe Area)** : Affichage parfait sur les écrans avec découpe de caméra ou barre de gestes Android (`env(safe-area-inset-*)`).

### 3. Fonctionnalités Essentielles pour Mobile
- **Maintien de l'écran allumé (Wake Lock)** : Bouton rapide ☀️ dans la barre de titre et bascule dans les paramètres pour empêcher la mise en veille pendant la lecture ou l'écoute.
- **Retour haptique / Vibrations légères** : Vibrations discrètes lors du changement de page, de l'enregistrement d'un marque-page, de la validation d'une révision de mémorisation ou de la fin d'une sourate.
- **Sauvegarde et Restauration par Fichier (.json)** :
  - **Exportation en 1 clic** : Génère un fichier de sauvegarde (`mushaf_backup_YYYY-MM-DD.json`) téléchargeable ou partageable.
  - **Importation par sélecteur de fichier** : Permet de choisir directement le fichier de sauvegarde depuis le stockage du téléphone sans copier-coller de texte.
- **Mode Plein Écran Immersif** : Un simple appui sur le texte coranique masque la barre supérieure et la barre de pagination pour une immersion totale dans la lecture.
- **Partage enrichi des versets** : Partage natif Android (`navigator.share`) avec texte arabe, numéro de verset et nom de sourate.
- **Notifications Toast flottantes** : Confirmation élégante et rapide pour chaque action (copie, sauvegarde, etc.).

---

## 🛠️ Guide de Compilation Automatique sur GitHub (Génération de l'APK)

### Étape 1 : Créer un nouveau dépôt sur GitHub
1. Connectez-vous sur [GitHub.com](https://github.com).
2. Cliquez sur le bouton vert **« New »** (ou **« Create repository »**).
3. Nommez le dépôt (ex. `mushaf-android-app`).
4. Choisissez la visibilité **Public** ou **Private** selon votre préférence.
5. Laissez la case *Initialize with README* décochée et cliquez sur **« Create repository »**.

### Étape 2 : Envoyer le code source sur GitHub
Ouvrez votre terminal dans le dossier du projet (`C:\Users\Biro\.gemini\antigravity\scratch\mushaf-app`) et exécutez les commandes suivantes :

```bash
git init
git add .
git commit -m "feat: mobile improvements, haptics, wakelock, intuitive navigation and apk workflow"
git branch -M main
git remote add origin https://github.com/VOTRE_NOM_UTILISATEUR/VOTRE_DEPOT.git
git push -u origin main
```

*(Remplacez l'URL par celle de votre dépôt GitHub).*

### Étape 3 : Compilation automatique (GitHub Actions)
1. Dès que vous avez fait le `git push`, rendez-vous sur la page de votre dépôt GitHub.
2. Cliquez sur l'onglet **« Actions »** en haut.
3. Vous verrez le workflow **« Build Android APK »** s'exécuter automatiquement.
4. Vous pouvez aussi le lancer manuellement à tout moment en cliquant sur **« Build Android APK »** dans la barre latérale gauche, puis sur le bouton **« Run workflow »**.
5. La compilation prend environ 2 à 3 minutes.

### Étape 4 : Télécharger le fichier APK prêt à installer
1. Une fois le workflow terminé avec succès (coche verte ✔️), cliquez sur la tâche qui vient de s'exécuter.
2. Descendez dans la section **« Artifacts »** en bas de page.
3. Cliquez sur **`mushaf-debug-apk`** pour télécharger le fichier ZIP contenant votre fichier `.apk` prêt à être installé sur votre smartphone Android !
