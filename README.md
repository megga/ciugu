# CIUGU

Site web du **cabinet dentaire CIUGU** — site statique (HTML / CSS / JS), entièrement autonome et hébergeable tel quel.

## Statut
- Tous les assets sont **locaux** : CSS, polices, images, icônes et animations — aucune dépendance externe, le site fonctionne hors-ligne.
- Marque unifiée sous le seul nom **CIUGU** : aucune autre dénomination dans les pages, les métadonnées, les noms de fichiers ou les liens.

## Structure (30 pages)
```
index.html                 — page d'accueil
home-pages/                — variantes d'accueil (V1, V2, V3)
about.html · services.html · service/oral-hygiene.html
doctors.html · doctor/john-carter.html
pricing.html · booking.html · checkout.html · product/premium.html
faqs.html · testimonials.html · coming-soon.html
blog-pages/ (V1·V2·V3) · blog-category/news.html · blog/<article>.html
contact-pages/ (V1·V2·V3)
template-pages/            — changelog, licenses, start-here, design-system
401.html · 404.html
css/ciugu.css              — feuille de style unique
fonts/                     — polices (texte + icônes)
images/                    — images PNG/SVG/JPG + animation Lottie
js/                        — jQuery + runtime d'animations/commerce
cms_pages.json             — mapping des pages dynamiques
```

## Prévisualisation locale
```bash
python3 -m http.server 8080
# puis ouvrir http://localhost:8080
```

## Déploiement (Cloudflare Pages)
```bash
npx wrangler pages project create ciugu --production-branch=main
npx wrangler pages deploy . --project-name=ciugu --commit-dirty=true
```
