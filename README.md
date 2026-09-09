# 🛰️ Progiciel Expert : GeoIRPI v6.1
## Direction de l'Environnement — Wilaya de Tizi Ouzou
### Modélisation Géo-Relationnelle Spatiale de l'Indice IRPI 

Ce dépôt présente le cadre algorithmique et la structure de données du modèle d'évaluation de la sécurité industrielle déconcentrée à l'échelle de la commune de Larbaâ Nath Irathen [Local].

---

### 🔬 1. Modélisation Thermodynamique et Potentiel Majeur
L'évaluation de l'Index de Risque Probabiliste Intégré ($\text{IRPI}_{\text{Spatial}}$) intègre la capacité quantitative de stockage de manière non linéaire au sein de son Potentiel Thermodynamique Majeur ($\Phi_{\text{Danger}}$) [Calcul]. Pour chaque entité géo-référencée, le calcul extrait la masse nominale $M$ (en kg) et l'enthalpie spécifique de la substance $\Delta H$ (en MJ/kg) [Calcul] :

$$\Phi_{\text{Danger}} = \log_{10} \Big( \text{Masse}_{\text{Stockée (kg)}} \times \text{Enthalpie}_{\text{Substance (MJ/kg)}} \Big)$$

Conformément aux principes de la mécanique des fluides régissant les explosions de gaz confinés ou les ruptures de canalisations haute pression, le modèle implémente la loi de cubication tridimensionnelle [Calcul]. Le rayon d'effet de l'onde de choc mécanique (seuil de surpression de 20 mbar pour les effets irréversibles) se calcule en fonction de la racine cubique de la charge équivalente [Calcul] :

$$R_{\text{Effet Létal}} = 4,4 \times \sqrt[3]{\text{Masse}_{\text{TNT (kg)}}}$$

---

### 📐 2. Modèle de Rendu Cartographique et Ségrégation des Calques
Afin de concilier la rigueur des calculs physiques au sol et l'ergonomie de l'interface utilisateur, le système expert sépare l'espace de décision de l'espace de rendu graphique [Calcul]. Le moteur visuel applique une formulation d'échelle indexée dynamiquement sur le rayon d'affichage de l'enquête publique, extrait de manière unitaire pour chaque activité d'après les tableaux officiels du Décret exécutif n° 06-198 [Calcul] :

$$R_{\text{Affichage}} = \mathcal{F}(\text{Rubrique\_JO})$$

Réglementairement, ce rayon d'affichage définit exclusivement le périmètre de consultation citoyenne et ne constitue pas une zone d'inconstructibilité absolue. Le continuum cartographique découple ainsi le calque des servitudes d'utilité publique fixes associées aux ouvrages de transport de fluides (couloir de 150 mètres du Décret présidentiel n° 07-144) du calque des périmètres d'isolement techniques variables calculés à l'échelle réelle en mètres sur le terrain [Local, Calcul].

---

### ⚖️ 3. Matrice de Constructibilité Graduée et Modèle Continu
Pour surmonter la rigidité des formalismes booléens et traiter les zones à forte densité d'infrastructures telles que Oued Aïssi, le progiciel « GeoIRPI v6.1 » introduit une fonction de constructibilité graduée par morceaux, segmentant le territoire en trois zones d'arbitrage [Local, Finance, Calcul] :

$$\text{Verdict}_{\text{Territorial}} = \begin{cases} \text{🔴 ZONE ROUGE} & \text{si } D_{\text{Gaz}} < 150 \text{ m} \ \vee \ D_{\text{Taddart}} < R_{\text{Effet Létal}} \\ \text{🟠 ZONE ORANGE} & \text{si } R_{\text{Effet Létal}} \le D_{\text{Taddart}} < R_{\text{Affichage}} \\ \text{🟢 ZONE VERTE} & \text{si } D_{\text{Taddart}} \ge R_{\text{Affichage}} \end{cases}$$

#### A. Les Règles d'Arbitrage Administratif
*   **🔴 ZONE ROUGE (Inconstructibilité Absolue) :** Le projet d'investissement du Titre 3 percute une servitude fixe Sonelgaz ou le rayon de surpression mécanique létal. Le logiciel ordonne le rejet automatique de l'acte d'urbanisme (Décret exécutif n° 15-19) [Local, Finance].
*   **🟠 ZONE ORANGE (Constructibilité sous Conditions) :** Le site respecte les seuils physiques létaux mais s'inscrit dans le périmètre d'enquête. Le visa est suspendu à l'obligation de mettre en œuvre des mesures de mitigation techniques lourdes (murs coupe-feu, barrières thermiques).
*   **🟢 ZONE VERTE (Homologation Étanche) :** L'établissement s'implante en zone stérile sécurisée, validant la libération des dossiers d'actes d'urbanisme.

#### B. Positionnement du Référentiel Technique International
Le modèle français (INERIS / Seveso) intervient de manière exclusive comme un scénario majorant alternatif destiné à tester la sensibilité des algorithmes d'effets dominos face aux Établissements Recevant du Public (ERP), sans se substituer à la souveraineté du droit public algérien [Calcul].

---
*Documentation technique de projet — Conforme au cadre réglementaire en vigueur au sein de la République Algérienne Démocratique et Populaire.*
