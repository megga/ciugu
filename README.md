# CIUGU

Base d'un site de **cabinet dentaire — « CIUGU »**, à partir d'un scrape brut du template Webflow **DentalCare X**.

## Source
- Template : https://dentalcaretemplate.webflow.io/
- Outil : [studiobloom/Reflow](https://github.com/studiobloom/reflow)
- Date du scrape : 03.06.2026

## Statut
- Scrape brut rebrandé **CIUGU** (12.06.2026) : nom de marque remplacé dans les 30 pages, style guide renommé en **design-system** (`template-pages/design-system.html`) — structure, classes, assets et animations IX2 intacts
- Toutes les pages, composants, images et animations Webflow IX2 préservés
- Rebrand restant : logo, copy, couleurs/typo, retrait du badge « Made in Webflow » et du popup promo BRIX, branchement des formulaires

## Intégrité vérifiée (preview locale)
- 30 pages HTML — toutes chargent
- 665 images sur l'ensemble des pages → **0 cassée**
- 205 assets (CSS, JS, SVG, fonts, background-images) → **0 manquant**

## Corrections appliquées au scrape brut
- Placeholder du panier Webflow Commerce (`w-dyn-bind-empty`) : le scraper avait réécrit son `src` vide en URL de page (`images/<page>.html`) sur 25 pages → remplacé par `images/placeholder.svg` (élément invisible, panier caché par défaut)
- Fichier `…care-&-service-….svg` : le `&` dans le nom est risqué selon l'hébergeur → renommé en `…care-and-service-….svg` (cohérent avec les fichiers frères) + refs HTML mises à jour

## Structure (30 pages, 436 images, 31 MB)
```
index.html                 — page vitrine du template
home-pages/                — home V1, V2, V3
about.html · services.html · service/oral-hygiene.html
doctors.html · doctor/john-carter.html
pricing.html · booking.html · checkout.html · product/premium.html
faqs.html · testimonials.html · coming-soon.html
blog-pages/ (V1·V2·V3) · blog-category/news.html · blog/<article>.html
contact-pages/ (V1·V2·V3)
template-pages/            — changelog, licenses, start-here, design-system (ex style-guide)
401.html · 404.html
images/                    — assets PNG/SVG/JPG
js/                        — jQuery + Webflow IX2 runtime
cms_pages.json             — dump CMS Webflow
```

## Déploiement (plus tard, après rebrand)
```bash
npx wrangler pages project create ciugu --production-branch=main
cd templates/ciugu
npx wrangler pages deploy . --project-name=ciugu --commit-dirty=true
```
> Ne pas modifier la structure HTML des éléments `data-w-id` (animations IX2 incluses dans le runtime).
