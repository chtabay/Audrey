# MAISON CASTEL — Cycle 1 : Collecte de données factuelles

## Objectif

Collecter des données **réelles et vérifiables** pour répondre aux 3 questions critiques
qui conditionnent la viabilité du projet avant toute modélisation financière.

---

## Agent 1 — RECHERCHE MARCHÉ

### Question critique
> À combien peut-on réalistement louer un bureau de 17 m² à Castelmaurou ou en périphérie NE Toulouse ?

### Missions de collecte

**1.1 Offre de bureaux existante**
- Annonces actuelles de bureaux à louer à Castelmaurou, L'Union, Balma, Rouffiac-Tolosan, Saint-Jean
- Prix au m²/an et au m²/mois pour des petites surfaces (10-30 m²)
- Caractéristiques des offres : surface, standing, services inclus, stationnement

**1.2 Espaces de coworking / bureaux partagés**
- Offres de coworking dans un rayon de 10 km (prix, formules, taux de remplissage si disponible)
- Tendance du marché : croissance ou saturation ?

**1.3 Données démographiques et économiques — Castelmaurou**
- Population, croissance, tranches d'âge (INSEE)
- CSP dominantes, taux d'actifs, revenus médians
- Nombre d'entreprises / établissements (base SIRENE ou données CCI)
- Secteurs d'activité dominants
- Projets d'urbanisme ou de développement en cours

**1.4 Contexte territorial**
- Bassin d'emploi : proximité Toulouse Nord-Est, aéronautique, zones d'activité
- Transports : desserte bus/métro, axes routiers, temps d'accès Toulouse centre
- Services : commerces, écoles, santé — attractivité pour des professionnels libéraux

### Livrable attendu
Fichier `CYCLE1_01_MARCHE.md` contenant :
- Tableau des annonces comparables avec prix
- Synthèse des données démographiques clés
- Fourchette de loyer estimée pour un bureau de 17 m² à Castelmaurou
- Forces et faiblesses de l'emplacement "face mairie"

---

## Agent 2 — RECHERCHE JURIDIQUE BAUX

### Question critique
> Bail précaire vs bail dérogatoire : lequel offre la flexibilité nécessaire pour garder le contrôle
> du RDC en vue du Projet P, sans risque de requalification en bail commercial ?

### Missions de collecte

**2.1 Bail commercial classique (3-6-9)**
- Articles du Code de commerce applicables (L.145-1 et suivants)
- Durée, droit au renouvellement, indemnité d'éviction
- Loyer : fixation, indexation (ILC / ILAT), plafonnement à la révision
- Répartition des charges (décret 2014 loi Pinel)
- Obligations du bailleur et du preneur

**2.2 Bail dérogatoire**
- Article L.145-5 du Code de commerce
- Durée maximale (3 ans depuis loi Pinel 2014)
- Conditions de validité
- Que se passe-t-il à l'échéance ? Risque de requalification automatique
- Renouvellement possible ou non

**2.3 Convention d'occupation précaire**
- Base juridique (jurisprudence, pas de texte spécifique)
- Condition sine qua non : circonstance objective justifiant la précarité
- Exemples de circonstances acceptées par les tribunaux
- Risque de requalification en bail commercial : cas concrets
- Durée, loyer, résiliation

**2.4 Comparatif structuré**
- Tableau comparatif : bail commercial / dérogatoire / convention précaire
- Avantages et risques pour le bailleur dans chaque cas
- Recommandation préliminaire pour le Projet Maison Castel (étage vs RDC)

**2.5 TVA et loyers commerciaux**
- Option pour la TVA sur loyers : quand est-elle obligatoire, quand est-elle avantageuse ?
- Impact sur la récupération de TVA sur les travaux

### Livrable attendu
Fichier `CYCLE1_02_JURIDIQUE_BAUX.md` contenant :
- Synthèse du cadre légal de chaque type de bail (avec articles de loi)
- Tableau comparatif
- Analyse des risques spécifiques au projet (RDC en précaire / dérogatoire)
- Points à valider avec un avocat

---

## Agent 3 — RECHERCHE URBANISME

### Question critique
> Quelle est la procédure exacte pour changer la destination du bien de "habitation"
> à "bureau/commerce" dans le PLU UMV1 de Castelmaurou ?

### Missions de collecte

**3.1 PLU de Castelmaurou — Zone UMV1**
- Règlement de la zone UMV1 : destinations autorisées, conditions
- Définition des destinations au sens du Code de l'urbanisme (article R.151-27)
- "Bureau" et "commerce" sont-ils dans la même sous-destination ?
- Existe-t-il des restrictions spécifiques en UMV1 ?

**3.2 Procédure de changement de destination**
- Déclaration préalable (article R.421-17 du Code de l'urbanisme) : dans quels cas ?
- Permis de construire : requis si changement de destination + modification de façade ou structure ?
- Les travaux prévus (intérieurs, PAC) déclenchent-ils un permis ?
- Pièces à fournir, délais d'instruction, formulaire CERFA applicable

**3.3 Normes ERP applicables**
- Classification ERP : 5e catégorie probable (< 100 personnes)
- Type d'ERP : W (bureaux) pour l'étage, M (commerce) ou W pour le RDC ?
- Obligations : sécurité incendie, issues de secours, alarme, extincteurs
- Accessibilité PMR : obligations pour un ERP existant, dérogations possibles pour l'étage
- Commission de sécurité : passage obligatoire ?

**3.4 Précédents locaux**
- Rechercher si d'autres changements de destination ont été accordés à Castelmaurou (délibérations publiques, PLU annoté)

### Livrable attendu
Fichier `CYCLE1_03_URBANISME.md` contenant :
- Extrait ou synthèse du règlement UMV1 applicable
- Procédure pas à pas pour le changement de destination
- Checklist ERP et PMR applicable au projet
- Risques et points de vigilance
- Points à valider avec la mairie

---

## Séquencement

```
                    MAINTENANT
                        │
          ┌─────────────┼─────────────┐
          ▼             ▼             ▼
    Agent 1          Agent 2       Agent 3
    MARCHÉ          JURIDIQUE    URBANISME
    (collecte)     (collecte)   (collecte)
          │             │             │
          ▼             ▼             ▼
    CYCLE1_01       CYCLE1_02     CYCLE1_03
    _MARCHE.md    _JURIDIQUE.md  _URBANISME.md
          │             │             │
          └─────────────┼─────────────┘
                        ▼
                REVUE PAR AUDREY
                (corrections, enrichissements)
                        │
                        ▼
                   CYCLE 2 :
              ATELIERS D'ANALYSE
```
