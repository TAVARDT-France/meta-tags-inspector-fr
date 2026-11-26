<p align="center">
  <a href="https://ag.tavardt.com/fr/">
    <img src="https://ag.tavardt.com/img/tavardt-banner.png" alt="TAVARDT" width="1024" />
  </a>
</p>

# Inspecteur de Balises Meta et Open Graph

[![Inspecteur Balises Meta](https://img.shields.io/badge/TAVARDT-Balises%20Meta-5b3cf5.svg)](https://tools.tavardt.com/fr/analyseur-balises-meta-seo/)
[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

Le **TAVARDT Inspecteur de Balises Meta et Open Graph** assure le contrôle automatisé des métadonnées HTML, du protocole Open Graph, des directives canoniques et de l'affichage dans les moteurs de recherche en France.

***

## Architecture des Métadonnées et Matrice Diagnostique

Les moteurs d'indexation et les réseaux sociaux utilisent les métadonnées pour analyser la pertinence d'un document et générer les vignettes de partage. Des balises manquantes ou mal calibrées entraînent une chute de visibilité et un taux de clic affaibli.

Cet outil diagnostique vérifie les longueurs recommandées pour le titre, la meta description, les balises de réseaux sociaux et le lien canonique sur une base de 100 points sans dépendances tierces.

Le moteur d'analyse examine les balises d'en-tête HTML conformément aux règles d'affichage des moteurs et des réseaux sociaux :

<table>
  <thead>
    <tr>
      <th>Balise d'En-tête</th><th>Critère de Validation</th><th>Déduction</th><th>Impact SEO et Réseaux Sociaux</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>Élément Title</strong></td><td>Exige la présence de <code>&lt;title&gt;</code>. Longueur idéale : 30-60 caractères. Pénalisé si &lt;20 caractères (-10 pts) ou &gt;70 caractères (-10 pts). Absent : -25 pts.</td><td>Jusqu'à -25 pts</td><td>Signal premier de positionnement et titre cliquable dans la SERP.</td>
    </tr>
    <tr>
      <td><strong>Meta Description</strong></td><td>Exige <code>&lt;meta name='description'&gt;</code>. Longueur idéale : 120-160 caractères. Pénalisé si &lt;70 caractères (-10 pts) ou &gt;175 caractères (-10 pts). Absent : -20 pts.</td><td>Jusqu'à -20 pts</td><td>Synthèse affichée influençant directement le taux de clic organique.</td>
    </tr>
    <tr>
      <td><strong>Protocole Open Graph</strong></td><td>Vérifie cinq propriétés obligatoires : <code>og:title</code>, <code>og:description</code>, <code>og:image</code>, <code>og:url</code> et <code>og:type</code>.</td><td>-5 pts par balise absente (Max -25 pts)</td><td>Permet l'affichage d'aperçus visuels enrichis sur LinkedIn, Facebook et Slack.</td>
    </tr>
    <tr>
      <td><strong>Directive Canonique</strong></td><td>Exige la présence de <code>&lt;link rel='canonical'&gt;</code> avec une URL cible absolue valide.</td><td>-10 pts</td><td>Évite les problématiques de contenu dupliqué et consolide l'autorité de page.</td>
    </tr>
    <tr>
      <td><strong>Échec de Connexion</strong></td><td>Expiration du délai de requête ou échec de négociation TLS/HTTP.</td><td>Score réinitialisé à 0</td><td>Inaccessibilité du serveur empêchant l'extraction des métadonnées.</td>
    </tr>
  </tbody>
</table>

### Échelle de Qualité et Niveaux d'État

L'utilitaire calcule un score global de qualité catégorisant la conformité des balises :

* <strong>85 à 100 (OPTIMAL)</strong> : Métadonnées parfaitement conformes ; title, description, canonique et Open Graph impeccables.
* <strong>65 à 84 (ACCEPTABLE)</strong> : Configuration opérationnelle présentant de légers écarts de longueur ou omissions mineures.
* <strong>0 à 64 (DEFICIENT)</strong> : Manquements critiques sur les balises majeures nuisant au référencement et au partage.

***

## Installation et Exécution

Conçu exclusivement avec les modules standards de Python 3.8+ sans dépendances externes.

```bash
git clone https://github.com/TAVARDT-France/meta-tags-inspector-fr.git
cd meta-tags-inspector-fr
```

### Exécution Standard CLI

```bash
python meta_inspector.py exemple.fr
```

### Sortie Structurée pour Pipelines en JSON

```bash
python meta_inspector.py exemple.fr -j
```

### Configuration du Délai d'Attente

```bash
python meta_inspector.py exemple.fr -j -t 15
```

***

## Recommandations et Intégrité Numérique en France

La maîtrise des métadonnées répond aux recommandations relatives à la sécurité et à l'intégrité des services numériques. Des métadonnées conformes préviennent les détournements d'aperçus et renforcent la fiabilité des communications.

Il est recommandé d'intégrer un contrôle automatisé des métadonnées dans les chaînes de déploiement continu afin de préserver la visibilité des applications web.

***

## Questions Fréquentes Techniques

### Quelle est la longueur optimale en caractères pour la balise title ?

L'inspecteur préconise une longueur comprise entre 30 et 60 caractères. Un titre de moins de 20 caractères perd 10 points pour manque de consistance sémantique, tandis qu'un titre de plus de 70 caractères subit 10 points de déduction en raison du risque de troncature. L'omission totale retire 25 points.

### Comment l'inspecteur évalue-t-il la balise meta description ?

Le système contrôle que la description se situe entre 120 et 160 caractères. En deçà de 70 caractères ou au-delà de 175 caractères, une pénalité de 10 points est appliquée. L'absence complète de la balise description engendre une déduction de 20 points.

### Quelles propriétés Open Graph sont obligatoires pour la conformité ?

Le script valide la présence de cinq balises fondamentales : <code>og:title</code>, <code>og:description</code>, <code>og:image</code>, <code>og:url</code> et <code>og:type</code>. Chaque propriété manquante retranche 5 points, pour un maximum de 25 points.

### Pourquoi la balise canonical est-elle indispensable en SEO technique ?

L'élément <code>&lt;link rel="canonical"&gt;</code> indique aux robots l'URL de référence faisant autorité, concentrant les signaux d'indexation et empêchant l'auto-cannibalisation de contenu. Son absence entraîne une déduction de 10 points.

### Que traduisent les scores de qualité et les niveaux d'optimisation ?

Un score de 85 à 100 correspond au statut OPTIMAL. De 65 à 84 points, le statut ACCEPTABLE indique une configuration fonctionnelle à ajuster, tandis qu'en dessous de 65 points, le statut DEFICIENT impose une remédiation urgente sur les balises maîtresses.

***

## Support Technique et Audit Spécialisé

Pour des audits approfondis de SEO technique, de conformité des métadonnées et de résilience web, contactez **TAVARDT**.

***

## Liens Utiles

* **Portail Institutionnel:** https://ag.tavardt.com/fr/
* **Suite de Diagnostic:** https://tools.tavardt.com/fr/
* **Contact Technique:** https://ag.tavardt.com/fr/contact/

***

### Licence
Distribué sous la licence MIT.

***

© 2026 TAVARDT. Tous droits réservés.
