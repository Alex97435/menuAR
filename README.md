# 🍽️ MenuAR Pro - Application de Réalité Augmentée pour Restaurants

Application complète permettant aux restaurateurs d'offrir une expérience AR à leurs clients pour visualiser les plats en 3D avant de commander.

![MenuAR](https://img.shields.io/badge/Version-1.0.0-blue)
![License](https://img.shields.io/badge/License-MIT-green)

## 🎯 Fonctionnalités

### ✅ Pour les Clients
- Menu interactif avec visualisation 3D des plats
- Réalité augmentée (placement du plat sur la table)
- Détails complets (ingrédients, allergènes, prix)
- Interface responsive mobile-first
- Aucune application à télécharger (WebAR)

### ✅ Pour les Restaurateurs
- Dashboard complet de gestion
- Ajout/modification de plats en temps réel
- Analytics et statistiques
- Génération de QR codes
- Multi-restaurant support

### ✅ Pour l'Administrateur
- Interface admin dédiée (alexandrebeton@gmail.com)
- Création et gestion de multiples restaurants
- Vue d'ensemble globale
- Statistiques consolidées

## 🚀 Déploiement sur Vercel (5 minutes)

### Prérequis
- Compte GitHub (gratuit)
- Compte Vercel (gratuit)

### Étape 1 : Push sur GitHub

```bash
# Dans votre terminal
cd menuar-pro

# Initialiser Git
git init

# Ajouter tous les fichiers
git add .

# Commit initial
git commit -m "Initial commit - MenuAR Pro"

# Créer le repository sur GitHub (via interface web)
# Puis lier et push :
git remote add origin https://github.com/VOTRE_USERNAME/menuar-pro.git
git branch -M main
git push -u origin main
```

### Étape 2 : Déployer sur Vercel

**Option A : Via Interface Web (Recommandé)**
1. Aller sur [vercel.com](https://vercel.com)
2. Cliquer "Add New Project"
3. Importer votre repo GitHub "menuar-pro"
4. Vercel détecte automatiquement la configuration
5. Cliquer "Deploy"
6. ✅ Votre site est en ligne en 30 secondes !

**Option B : Via CLI**
```bash
# Installer Vercel CLI
npm i -g vercel

# Déployer
vercel

# Déployer en production
vercel --prod
```

### Étape 3 : Configurer votre domaine (Optionnel)

1. Dans Vercel Dashboard → Settings → Domains
2. Ajouter votre domaine personnalisé
3. Suivre les instructions DNS

## 📁 Structure du Projet

```
menuar-pro/
├── public/                  # Fichiers publics
│   ├── index.html          # Landing page
│   ├── admin.html          # Interface admin
│   ├── dashboard.html      # Dashboard restaurateur
│   └── menu.html           # Menu AR client
├── vercel.json             # Configuration Vercel
├── package.json            # Dépendances
├── .gitignore             # Fichiers ignorés
└── README.md              # Ce fichier
```

## 🔐 Connexion Admin

**Interface Admin :** `https://votre-site.vercel.app/admin`

**Identifiants par défaut :**
- Email : `alexandrebeton@gmail.com`
- Mot de passe : `admin123`

⚠️ **IMPORTANT :** Changez le mot de passe dans `public/admin.html` ligne 296 avant de déployer en production !

```javascript
// Dans admin.html, ligne 296
const ADMIN_PASSWORD = 'VOTRE_NOUVEAU_MOT_DE_PASSE_SECURISE';
```

## 📱 Utilisation

### Pour créer un nouveau restaurant :

1. Connectez-vous à `/admin` avec vos identifiants
2. Cliquez "Nouveau restaurant"
3. Remplissez les informations
4. Le restaurant est créé avec un ID unique

### Pour gérer un restaurant :

1. Dans l'admin, cliquez sur l'icône Dashboard (📊)
2. Ajoutez vos plats avec le bouton "+ Ajouter un plat"
3. Générez vos QR codes
4. Imprimez et placez-les sur vos tables

### Pour les clients :

1. Scanner le QR code sur la table
2. Le menu s'ouvre automatiquement
3. Cliquer sur un plat pour voir les détails
4. Cliquer "Voir en AR" pour la réalité augmentée

## 🎨 Personnalisation

### Changer les couleurs

Dans chaque fichier HTML, modifiez les variables CSS (dans la balise `<style>`) :

```css
:root {
    --primary: #0F172A;      /* Couleur principale */
    --accent: #3B82F6;       /* Couleur d'accentuation */
    --accent-light: #DBEAFE; /* Accent clair */
}
```

### Ajouter votre logo

Remplacez le texte "MenuAR" dans les fichiers HTML par :

```html
<img src="/logo.png" alt="Votre Logo" style="height: 32px;">
```

### Modifier les plans tarifaires

Dans `public/index.html`, section pricing (lignes 300-400).

## 🔧 Développement Local

```bash
# Installer les dépendances
npm install

# Lancer le serveur de développement
npm run dev

# Ouvrir dans le navigateur
# http://localhost:3000
```

## 🌟 Fonctionnalités à Venir (Roadmap)

### Version 1.1 (Court terme)
- [ ] Intégration vrais modèles 3D (.glb)
- [ ] Backend API avec base de données
- [ ] Authentification sécurisée (JWT)
- [ ] Upload de photos pour créer des modèles 3D

### Version 1.2 (Moyen terme)
- [ ] Application mobile native
- [ ] Intégration systèmes de caisse
- [ ] Commande directe depuis l'AR
- [ ] Paiement en ligne

### Version 2.0 (Long terme)
- [ ] IA pour création automatique de modèles 3D
- [ ] Recommandations personnalisées
- [ ] Programme de fidélité
- [ ] Analytics avancés avec ML

## 🔒 Sécurité

### Pour la Production

**1. Changez le mot de passe admin**
Dans `public/admin.html` :
```javascript
const ADMIN_PASSWORD = 'votre_mot_de_passe_securise';
```

**2. Ajoutez des variables d'environnement Vercel**
```bash
vercel env add ADMIN_PASSWORD
```

**3. Implémentez une vraie authentification**
- Utilisez Firebase Auth, Auth0, ou NextAuth
- Ajoutez JWT tokens
- Hashage des mots de passe (bcrypt)

**4. HTTPS**
- Automatique sur Vercel ✅
- Obligatoire pour WebAR

## 📊 Analytics

Le projet utilise localStorage pour la démo. Pour la production :

**Recommandations :**
- Google Analytics 4
- Vercel Analytics (inclus)
- Mixpanel pour événements détaillés
- Custom backend pour tracking précis

## 💰 Monétisation

### Pricing suggéré :
- **Starter** : 49€/mois (15 plats, 1 restaurant)
- **Professional** : 99€/mois (50 plats, 3 restaurants)
- **Enterprise** : Sur mesure (illimité)

### ROI Client :
Un restaurant avec un ticket moyen de 25€ :
- 3 plats premium/jour supplémentaires
- = 75€/jour × 30 = 2,250€/mois CA additionnel
- Avec 60% de marge = 1,350€/mois profit
- Coût MenuAR = 99€/mois
- **ROI = 1,251€/mois net (x13.6)**

## 🐛 Dépannage

### Le site ne se charge pas
- Vérifiez que tous les fichiers sont dans `/public`
- Vérifiez `vercel.json` est correct
- Consultez les logs Vercel

### AR ne fonctionne pas
- Vérifiez que vous êtes en HTTPS
- Testez sur un smartphone récent (iOS 12+, Android 8+)
- Chrome ou Safari uniquement pour WebAR

### localStorage plein
- Limite de 5-10MB selon navigateur
- Migrez vers une vraie base de données

## 🤝 Support

**Email :** alexandrebeton@gmail.com

**Pour signaler un bug :**
Créez une issue sur GitHub avec :
- Description du problème
- Étapes pour reproduire
- Navigateur et version
- Screenshots si possible

## 📄 Licence

MIT License - Vous êtes libre d'utiliser ce code pour votre business.

## 🙏 Remerciements

- [Model Viewer](https://modelviewer.dev/) pour le composant WebAR
- [Inter Font](https://rsms.me/inter/) pour la typographie
- [Vercel](https://vercel.com) pour l'hébergement

## 🚀 Prochaines Étapes

1. ✅ Push sur GitHub
2. ✅ Déployer sur Vercel
3. 📝 Créer votre premier restaurant
4. 📱 Générer les QR codes
5. 🎯 Démarcher vos premiers clients !

---

**Fait avec ❤️ pour révolutionner l'expérience restaurant**

*Version 1.0.0 - 2025*
