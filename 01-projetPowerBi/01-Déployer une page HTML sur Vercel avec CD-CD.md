# **Tutoriel : Déployer une page HTML sur Vercel avec CI/CD**

Ce guide explique comment déployer une page HTML sur Vercel avec CI/CD en utilisant GitHub. Chaque modification sera automatiquement déployée.

---

## **1. Préparer le projet HTML**
Crée un dossier et un fichier `index.html`.

### **Créer un dossier et entrer dedans**
```sh
mkdir mon-site-html
cd mon-site-html
```

### **Créer un fichier `index.html`**
```sh
touch index.html
```

### **Ajouter du contenu dans `index.html`**
```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ma Page sur Vercel</title>
</head>
<body>
    <h1>Bienvenue sur mon site déployé avec Vercel</h1>
    <p>Ce site est déployé avec Vercel et GitHub pour CI/CD.</p>
</body>
</html>
```

---

## **2. Initialiser un dépôt Git**
L'objectif est de stocker le code sur GitHub.

### **Initialiser un dépôt Git**
```sh
git init
```

### **Créer un fichier `.gitignore`**
```sh
touch .gitignore
echo "node_modules/" >> .gitignore
echo ".vercel/" >> .gitignore
```

### **Faire un premier commit**
```sh
git add .
git commit -m "Premier commit : ajout de index.html"
```

### **Créer un dépôt GitHub**
1. Aller sur GitHub.
2. Créer un nouveau dépôt.
3. Copier l’URL du dépôt.

### **Lier le dépôt local à GitHub**
```sh
git remote add origin https://github.com/ton-user/mon-site-html.git
git branch -M main
git push -u origin main
```

---

## **3. Installer Vercel et déployer**
Vercel permet d’héberger le site et de gérer les mises à jour automatiques.

### **Installer Vercel CLI**
```sh
npm install -g vercel
```

### **Se connecter à Vercel**
```sh
vercel login
```

### **Déployer une première fois**
```sh
vercel
```
Répondre aux questions :
- "In which directory is your code located?" → Entrée.
- "Want to deploy from a different Git repository?" → Non.
- "Which framework preset?" → Autre (Static Site).
- "Link to existing project?" → Non.
- "What's your project’s name?" → Entrée ou nom personnalisé.
- "Which scope do you want to deploy to?" → Sélectionner le compte.

Vercel affiche une URL où le site est déployé.

---

## **4. Activer CI/CD avec GitHub**
Vercel doit être connecté à GitHub pour redéployer automatiquement les mises à jour.

### **Lier GitHub à Vercel**
1. Aller sur [vercel.com](https://vercel.com) et se connecter.
2. Aller dans "Dashboard" > "Import Project".
3. Sélectionner "From Git Repository".
4. Connecter GitHub et sélectionner le dépôt `mon-site-html`.
5. Cliquer sur "Deploy".

Vercel surveille maintenant le dépôt et redéploie chaque changement.

---

## **5. Tester CI/CD**
Chaque modification sur GitHub sera automatiquement mise en ligne.

### **Modifier `index.html`**
Ajouter une ligne dans `index.html` :
```html
<p>Mise à jour automatique via CI/CD.</p>
```

### **Envoyer la modification sur GitHub**
```sh
git add index.html
git commit -m "Mise à jour du contenu"
git push origin main
```

### **Vérifier le déploiement**
1. Aller sur Vercel Dashboard > Projet.
2. Aller dans "Deployments".
3. Vérifier le dernier déploiement.

Le site est mis à jour automatiquement.

---

## **Résumé**
1. Création du projet HTML.
2. Dépôt sur GitHub.
3. Premier déploiement manuel avec Vercel.
4. Activation du CI/CD avec GitHub.
5. Test de mise à jour automatique.

Le site est maintenant en ligne et chaque modification sur GitHub est automatiquement publiée.
