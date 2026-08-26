# 🛰️ Progiciel Expert : GeoIRPI v6.0
## Direction de l'Environnement — Wilaya de Tizi Ouzou
### Modélisation Géo-Relationnelle Spatiale de l'Indice IRPI par Approche de Droit Comparé (Algérie-France)

Ce dépôt présente le cadre algorithmique et la structure de données du modèle d'évaluation de la sécurité industrielle déconcentrée à l'échelle de la commune de Larbaâ Nath Irathen [Local].

---

### 🔬 1. Modélisation Thermodynamique et Loi de Cubication
L'évaluation de l'Index de Risque Probabiliste Intégré ($\text{IRPI}_{\text{Spatial}}$) intègre la capacité quantitative de stockage de manière non linéaire au sein de son spectre cinétique de danger ($\Phi_{\text{Danger}}$) [Calcul]. Pour chaque entité géo-référencée, le calcul extrait la masse nominale $M$ (en kg) et l'enthalpie spécifique de la substance $\Delta H$ (en MJ/kg) [Calcul] :

$$\Phi_{\text{Danger}} = \log_{10} \Big( \text{Masse}_{\text{Stockée (kg)}} \times \text{Enthalpie}_{\text{Substance (MJ/kg)}} \Big)$$

Conformément aux principes de la mécanique des fluides régissant les explosions de gaz confinés ou les ruptures de canalisations haute pression, le modèle abandonne les lois de surface pour implémenter la loi de cubication tridimensionnelle [Calcul]. Le rayon d'effet de l'onde de choc mécanique (seuil de surpression de 20 mbar pour les effets irréversibles) se calcule en fonction de la racine cubique de la charge équivalente [Calcul] :

$$R_{\text{Surpression 20mbar}} = 4,4 \times \sqrt[3]{\text{Masse}_{\text{TNT (kg)}}}$$

---

### 📐 2. Modèle de Rendu Graphique par Rubriques d'Activités
Afin de concilier la rigueur des calculs physiques au sol et l'ergonomie cartographique de l'espace municipal, le système expert sépare l'espace de décision de l'espace de rendu graphique [Calcul]. Le moteur visuel applique une formulation d'échelle indexée dynamiquement sur le rayon d'affichage de l'enquête publique, extrait de manière unitaire pour chaque activité d'après les tableaux officiels du Décret exécutif n° 06-198 [Calcul] :

$$R_{\text{Affichage}} = \mathcal{F}(\text{Rubrique\_JO})$$

Cette configuration préserve la lisibilité de la carte du village et de l'artisanat local sans altérer la sincérité du calcul physique d'origine, exécuté à l'échelle réelle en mètres sur le terrain [Local, Calcul].

---

### ⚖️ 3. Formalisme Booléen et Double Verrou de Contrôle
L'évaluation finale des demandes d'implantation (Titre 3) s'exécute à travers une fonction logique binaire d'homologation administrative [Finance, Calcul] :

$$\text{Verdict}_{\text{Final}} = \mathbf{1}_{\text{Droit\_Algérien}} \times \mathbf{1}_{\text{Expertise\_INERIS}}$$

Où chaque fonction indicatrice ($\mathbf{1}$) est définie de manière déterministe par la superposition spatiale (*Map Overlay*) de trois calques locaux (Industriel, Anthropique et Énergétique) via des jointures relationnelles de Niveau 2 ($\bowtie$) [Calcul] :

#### A. Le Verrou Légal Exécutoire (Souveraineté Nationale)
La décision administrative de délivrance ou de rejet de l'acte d'urbanisme (Décret exécutif n° 15-19) est asservie de manière exclusive à la conformité aux décrets algériens n° 07-144 (servitude de 150 mètres des gazoducs) et n° 06-198 (rayons d'isolement de la nomenclature) [Local, Finance] :

$$\mathbf{1}_{\text{Droit\_Algérien}} = \sigma_{(D_{\text{Gaz}} \ge 150) \, \wedge \, (D_{\text{Taddart}} \ge \text{Rayon}_{\text{Rubrique}})}$$

#### B. Le Module d'Expertise Subsidiaire (Consultatif)
Les normes techniques françaises et européennes (PPRT / INERIS) interviennent uniquement à titre de conseil d'ingénierie pour évaluer l'exposition des Établissements Recevant du Public (ERP) face aux risques d'effets dominos [Calcul] :

$$\mathbf{1}_{\text{Expertise\_INERIS}} = \sigma_{D_{\text{ERP}} \ge R_{\text{Surpression}}(\text{Seveso})}$$

Toute infraction constatée sur les distances réglementaires algériennes entraîne l'effondrement instantané de l'indice ($\text{Verdict}_{\text{Final}} = 0$), déclenchant le rejet automatique de l'acte d'urbanisme au niveau du guichet unique de la commune [Finance, Calcul].

---
*Documentation technique de projet — Conforme au cadre réglementaire en vigueur au sein de la République Algérienne Démocratique et Populaire.*
