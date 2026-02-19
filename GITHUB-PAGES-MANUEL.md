# GitHub Pages - Déploiement Manuel (sans Git local)

## 🚀 ÉTAPES SIMPLES

### 1. Créer le repository GitHub
1. Allez sur [github.com](https://github.com)
2. Cliquez sur **"New repository"**
3. Nom : `pinterest-clone-website`
4. Public (recommandé pour Pages)
5. Cliquez **"Create repository"**

### 2. Uploader les fichiers
1. Dans votre repository, cliquez sur **"Add file"** → **"Upload files"**
2. Glissez-déposez TOUS vos fichiers du projet SAUF :
   - `node_modules/`
   - `dist/`
3. Commit changes : "Initial commit"
4. Cliquez **"Commit changes"**

### 3. Activer GitHub Pages
1. Dans votre repository, allez dans **Settings**
2. Dans le menu de gauche, cliquez sur **Pages**
3. **Source** : Sélectionnez **"Deploy from a branch"**
4. **Branch** : Choisissez **"main"**
5. **Folder** : **"/ (root)"**
6. Cliquez **"Save"**

### 4. Attendre le déploiement
GitHub va construire votre site (2-5 minutes)
L'URL sera : `https://VOTRE_USERNAME.github.io/pinterest-clone-website`

## 🔧 SI ÇA MARCHE PAS

### Option A : Utiliser le dossier `dist`
1. Suivez les étapes 1-2 ci-dessus
2. Dans Pages settings, sélectionnez **"/dist"** comme dossier
3. Uploadez aussi le dossier `dist` complet

### Option B : Netlify (plus simple)
1. Allez sur [netlify.com](https://netlify.com)
2. Glissez le DOSSIER `dist` dans la zone de déploiement
3. C'est fini !

## 📋 FICHIERS À UPLOADER

✅ **À uploader :**
- `src/` (tout le dossier)
- `package.json`
- `package-lock.json`
- `vite.config.ts`
- `tsconfig.json`
- `index.html`
- `.gitignore`

❌ **À ne PAS uploader :**
- `node_modules/`
- `dist/` (sauf si option A)

## 🎯 RÉSULTAT FINAL

Votre site sera accessible :
`https://VOTRE_USERNAME.github.io/pinterest-clone-website`

C'est gratuit, rapide et hébergé par GitHub !
