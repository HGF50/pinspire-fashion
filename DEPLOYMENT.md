# Pinterest Clone - Déploiement en ligne

## Options de déploiement gratuites et simples

### 1. Vercel (Recommandé)
- **Avantages**: Très facile, déploiement automatique depuis GitHub, domaine gratuit
- **Étapes**:
  1. Créez un compte sur [vercel.com](https://vercel.com)
  2. Connectez votre compte GitHub
  3. Importez votre repository
  4. Vercel détecte automatiquement votre projet React/Vite
  5. Cliquez sur "Deploy"

### 2. Netlify
- **Avantages**: Interface simple, déploiement par drag & drop
- **Étapes**:
  1. Créez un compte sur [netlify.com](https://netlify.com)
  2. Cliquez sur "New site from Git"
  3. Connectez GitHub et sélectionnez votre repository
  4. Configurez: Build command `npm run build`, Publish directory `dist`
  5. Cliquez sur "Deploy site"

### 3. GitHub Pages
- **Avantages**: Gratuit si vous utilisez déjà GitHub
- **Étapes**:
  1. Ajoutez ce script à votre `package.json`:
     ```json
     "homepage": "https://[VOTRE_USERNAME].github.io/pinterest-clone-website",
     "predeploy": "npm run build",
     "deploy": "gh-pages -d dist"
     ```
  2. Installez gh-pages: `npm install --save-dev gh-pages`
  3. Exécutez: `npm run deploy`

## Préparation avant déploiement

### 1. Créer un repository GitHub
```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/VOTRE_USERNAME/pinterest-clone-website.git
git push -u origin main
```

### 2. Vérifier la configuration
Assurez-vous que votre `vite.config.ts` est configuré pour le déploiement:

```typescript
import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'

export default defineConfig({
  plugins: [react()],
  base: '/', // Changez si nécessaire pour certains hébergeurs
  build: {
    outDir: 'dist'
  }
})
```

## Étapes rapides avec Vercel (le plus simple)

1. **Poussez votre code sur GitHub**
2. **Allez sur vercel.com**
3. **Connectez votre compte GitHub**
4. **Cliquez sur "New Project"**
5. **Sélectionnez votre repository `pinterest-clone-website`**
6. **Cliquez sur "Deploy"**

Vercel va automatiquement:
- Détecter que c'est un projet Vite
- Installer les dépendances
- Builder le projet
- Le déployer avec une URL comme `https://your-project.vercel.app`

## Après le déploiement

Votre site sera accessible via:
- **Vercel**: `https://votre-projet.vercel.app`
- **Netlify**: `https://votre-projet.netlify.app`
- **GitHub Pages**: `https://votre-username.github.io/pinterest-clone-website`

## Problèmes courants

### localStorage et déploiement
- Le localStorage fonctionne parfaitement en production
- Les données sont sauvegardées dans le navigateur de chaque utilisateur
- Chaque utilisateur a ses propres données

### Images et assets
- Vos images uploadées sont converties en base64
- Elles sont stockées dans le localStorage du navigateur
- Pas besoin de serveur d'images pour l'instant

## Conseil
Commencez avec **Vercel**, c'est la solution la plus simple et la plus rapide pour les projets React/Vite.
