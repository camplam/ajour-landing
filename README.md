# AJOUR — Landing page

Site vitrine statique (HTML/CSS/JS, sans framework ni dépendance).

## Lancer en local

```bash
npm install   # aucune dépendance à installer, valide juste l'environnement
npm run build # vérifie que index.html existe (aucune compilation nécessaire)
npm run dev   # sert le site sur http://localhost:3000
```

Ou plus simplement, ouvrir `index.html` directement dans un navigateur.

## Déployer sur Vercel

1. Pousser ce dossier sur un repo GitHub.
2. Dans Vercel : "Add New Project" → importer le repo.
3. Aucune configuration de build requise (Framework Preset : "Other" / Static). Vercel sert `index.html` tel quel.

## À configurer avant la mise en ligne (bloquant)

- **Formulaire « Rejoindre la liste »** : le formulaire ne fait qu'afficher un message de confirmation côté client — **il n'envoie encore le courriel nulle part**. Avant le lancement, branche-le à un vrai service (Formspree, Airtable, Google Sheets via une fonction serverless, Mailchimp, etc.) : modifie le gestionnaire `submit` dans `index.html` (section `<script>` en bas de page).
- **Lien « Se connecter »** : pointe vers `https://app.ajour.ca/login` — à ajuster si l'URL réelle du portail diffère.
- **Domaine** : les balises `canonical` et Open Graph pointent vers `https://ajour.ca/` — à ajuster si le domaine final est différent.

## Configuration éditable

Le prix et le nombre de places fondatrices sont centralisés dans une seule constante, en bas de `index.html` :

```js
const AJOUR_CONFIG = { price: 99, seats: 5 };
```

## Structure

```
index.html       page unique
favicon.svg       icône du site
assets/           logos, images, image Open Graph
```

## Vérifié avant livraison

- Responsive mobile (aucune largeur fixe qui déborde), navigation desktop/mobile, ancre de chaque lien de section.
- Aucune clé ni secret exposé dans le code (le site n'a pas de backend).
- Métadonnées SEO, Open Graph, Twitter Card, favicon et icône iOS en place.
- Images optimisées ; asset inutilisé retiré.

- 
