
# Guide complet ultra-structuré : Blog Astro + Tailwind CSS + SEO avancé
## **Objectif :**
Créer facilement et rapidement un blog SEO-friendly, minimaliste, performant, pour générer un maximum de trafic vers tes formations Thinkific.

---

# 🟢 **ÉTAPE 1 : Commandes pour démarrer le projet Astro + Tailwind**

Ouvre ton terminal, copie-colle ces commandes **exactement :**

```bash


# Initialisation projet Astro
npm create astro@latest passyourcodinginterview
cd passyourcodinginterview
npm install


# Installer Tailwind CSS avec Astro
npm install -D tailwindcss@3 postcss autoprefixer @astrojs/tailwind
npx tailwind init -p


# Démarrer le serveur
npm run dev
CTL + C
code .


```

Modifie `astro.config.mjs` avec Tailwind :



```js

// @ts-check
import { defineConfig } from 'astro/config';
import mdx from '@astrojs/mdx';
import sitemap from '@astrojs/sitemap';
import tailwind from '@astrojs/tailwind';

// https://astro.build/config
export default defineConfig({
	site: 'https://passyourcodinginterview.com',
	integrations: [mdx(), sitemap(), tailwind()],
});


```

Configure Tailwind (`tailwind.config.js`) :

```js

/** @type {import('tailwindcss').Config} */
export default {
  content: [
    "./index.html",
    "./src/**/*.{astro,html,md,mdx,mjs,ts,tsx,jsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}

```

Lance le projet :
```bash
npm run dev
```

Ton blog Astro + Tailwind est prêt sur : `http://localhost:4321`

