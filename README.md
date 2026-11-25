# Inspecteur de Balises Meta et Open Graph

[![Inspecteur Balises Meta](https://img.shields.io/badge/TAVARDT-Balises%20Meta-5b3cf5.svg)](https://tools.tavardt.com/fr/analyseur-balises-meta-seo/)
[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

Audit technique des metadonnees HTML, controle de longueur des balises title et meta description, apercu des cartes sociales et indexation.

***

## Capacites d'Audit des Metadonnees et Reseaux Sociaux

* **Controle des Titres et Descriptions**: Analyse des longueurs recommandees pour les balises title et meta description.
* **Protocole Open Graph**: Validation des proprietes og:title, og:description, og:image, og:url et og:type.
* **Cartes Twitter Cards**: Verification de la conformite des cartes de partage social.
* **Directives d'Indexation**: Inspection des balises meta robots et presence du lien canonique.
* **Score de Qualite d'Extrait**: Evaluation chiffree sur 100 points avec etapes d'amelioration redactionnelle.

***

## Installation et Utilisation

Necessite Python 3.8 ou superieur, sans bibliotheque tierce.

```bash
git clone https://github.com/TAVARDT-France/meta-tags-inspector-fr.git
cd meta-tags-inspector-fr
python meta_inspector.py exemple.fr
```

Pour un rapport structure en JSON:

```bash
python meta_inspector.py exemple.fr -json
```

***

## Conseil en Referencement Technique et SEO

Pour des projets avances d'optimisation conformes aux exigences Standards W3C et Bonnes Pratiques SEO, contactez **TAVARDT**.

***

## Liens Utiles

* **Portail Entreprise:** https://ag.tavardt.com/fr/
* **Suite de Diagnostic:** https://tools.tavardt.com/fr/
* **Contact Technique:** https://ag.tavardt.com/fr/contact/

***

### Licence
Distribué sous la licence MIT.

***

© 2026 TAVARDT. Tous droits réservés.
