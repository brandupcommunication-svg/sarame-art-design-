# Sarame Art Design — site vitrine

Site one-page + page contact pour **Sarame Art Design** (ébénisterie d'art, artisanat Saramaca, Guyane).

**Stack :** Next.js 15 (App Router) · TypeScript · Tailwind CSS · GSAP · Framer Motion · Resend · lucide-react.

---

## Lancer en local

```bash
npm install
npm run dev
# http://localhost:3000
```

Formulaire de contact : copier `.env.example` en `.env.local` et renseigner la clé Resend.

---

## Déployer sur Vercel

### Option A — Vercel CLI (le plus rapide, sans GitHub)
```bash
npm i -g vercel      # une seule fois
vercel               # suivre les questions (login, projet)
vercel --prod        # déploiement en production
```

### Option B — via GitHub (recommandé pour le suivi)
1. Pousser ce dossier sur un dépôt GitHub.
2. Sur https://vercel.com → **Add New… → Project** → importer le dépôt.
3. Framework détecté automatiquement : **Next.js**. Laisser les réglages par défaut.
4. Déployer.

### Variables d'environnement (à définir dans Vercel → Settings → Environment Variables)
Nécessaires uniquement pour activer l'envoi du formulaire de contact :

| Variable         | Valeur                                             |
|------------------|----------------------------------------------------|
| `RESEND_API_KEY` | *(ta clé depuis https://resend.com)*               |
| `CONTACT_TO`     | `sarameartdesign888@gmail.com`                     |
| `CONTACT_FROM`   | `Sarame Art Design <onboarding@resend.dev>`        |

> Sans `RESEND_API_KEY`, le site se déploie et fonctionne ; seul l'envoi du
> formulaire renverra une erreur « service non configuré ». Le reste du site
> (design, animations, contenu) ne dépend d'aucune variable.

---

## À finaliser
- Remplacer les **photos placeholder** des réalisations (`public/creations/*.svg`)
  par de vraies photos HD.
- Ajouter les **logos** partenaires/clients si souhaité (actuellement en texte).
- Renseigner `RESEND_API_KEY` pour le formulaire.

## Régénérer les visuels
```bash
node scripts/gen-placeholders.mjs   # visuels réalisations
node scripts/gen-motif.mjs          # motif d'atmosphère SARAME
```
