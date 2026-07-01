# 🩺 Analyse Biostatistique : Essai Clinique de Phase II (CardioX vs Placebo)

## 📋 Présentation du Projet
Ce projet présente l'analyse de données brutes issues d'un essai clinique fictif de Phase II (millésime 2026) évaluant l'efficacité et la tolérance d'un nouveau traitement contre l'hypertension artérielle systolique : le **CardioX**. 

L'objectif de cette étude est de nettoyer les données de l'échantillon, de quantifier l'effet thérapeutique par rapport à un **Placebo**, d'analyser le profil des patients et d'émettre des recommandations biostatistiques quant au passage en Phase III.

---

## 📊 Le Jeu de Données
L'étude porte sur un échantillon de 10 patients ($N = 10$) répartis équitablement entre le groupe de traitement (*CardioX*) et le groupe témoin (*Placebo*).

*   **PAS_Avant** : Pression Artérielle Systolique avant traitement (en mmHg).
*   **PAS_Apres** : Pression Artérielle Systolique après traitement (en mmHg).
*   **Effet_Secondaire** : Tolérance clinique rapportée par le patient.

---

## 🛠️ Méthodologie & Formules Appliquées (Google Sheets / Excel)

Pour mener à bien cette analyse, le jeu de données a été enrichi à l'aide de formules dynamiques et de fonctions conditionnelles avancées :

1. **Calcul de la chute de tension absolue (PAS) :**
   ```excel
   =PAS_Avant - PAS_Apres

   Détermination de l'efficacité clinique (Statut) :
Le seuil de réussite thérapeutique est fixé par le protocole médical à une baisse stricte supérieure à 15 mmHg.
=IF(Chute_PAS > 15 ; "Réussi" ; "Échec")

Segmentation et calcul des moyennes de groupe :
Utilisation de la fonction matricielle dynamique pour isoler les cohortes :
=FILTER(A2:J11 ; B2:B11 = "CardioX")

Puis calcul des indicateurs clés via =AVERAGE() (=MOYENNE()).

🧠 Interprétation Biostatistique & Clinique
1. Efficacité Clinique
   L'effet thérapeutique du CardioX est mathématiquement et cliniquement démontré. Avec une baisse moyenne de 24,6 mmHg contre seulement 1,4 mmHg pour le Placebo,
   l'écart de performance (> 23 mmHg) prouve que l'action du principe actif l'emporte largement sur l'effet contextuel du placebo.

2. Uniformité du Profil Patient
   L'analyse croisée des variables physiologiques indique que le CardioX agit de manière uniforme sur cet échantillon. L'efficacité maximale reste supérieure au seuil critique de 15 mmHg,
   indépendamment du sexe ou de la distribution d'âge (allant de 38 ans avec $-30\text{ mmHg}$ à 70 ans avec $-35\text{ mmHg}$).

3. Rapport Bénéfice / Risque (Phase III)
   Recommandation : Autorisation de passage en Phase III.
   En pharmacovigilance, l'absence totale d'effets indésirables est une utopie biologique. Face aux risques mortels liés à une hypertension non contrôlée (AVC, infarctus)
   les effets secondaires recensés sous CardioX (1 cas de céphalée, 1 cas de nausée) sont jugés mineurs et transitoires. Le rapport bénéfice/risque est donc hautement favorable.

4. Limites Statistiques de l'Étude
   En tant que biostatisticien, la limite majeure identifiée réside dans la puissance statistique de l'échantillon ($N = 10$). Un effectif aussi réduit ne permet pas de généraliser les conclusions à une population globale,
   ni de calculer une $p$-value robuste (test t de Student) exempte de biais de fluctuation d'échantillonnage. Le passage à la Phase III est précisément requis pour valider ces tendances sur une cohorte à grande échelle.

🔧 Outils utilisés : Google Sheets, Formules Logiques & Matricielles, Analyse de données cliniques.
