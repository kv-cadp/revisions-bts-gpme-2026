# Note d'audit pédagogique - Banque QCM E6 SFPME

**Production** : Banque de 350 questions QCM
**Couverture** : 7 activités du référentiel BTS GPME (A4.1 à A4.7)
**Date** : 10 mai 2026
**Lecteur cible** : Kévin Vidard, à valider avant push GitHub Pages

---

## 1. Synthèse de la production

| Activité | Intitulé | Nombre de questions |
|---|---|---|
| A4.1 | Recherche de clientèle et contact | 50 |
| A4.2 | Administration des ventes et communication interne | 50 |
| A4.3 | Administration du personnel | 50 |
| A4.4 | Communication institutionnelle | 50 |
| A4.5 | Analyse de l'activité | 50 |
| A4.6 | Diagnostic financier | 50 |
| A4.7 | Tableaux de bord et reporting | 50 |
| | **Total** | **350** |

Le fichier produit est un HTML autonome (131 ko) intégrant les 350 questions, le moteur d'affichage, la persistance localStorage et le mailto récap. Aucune dépendance externe sauf Google Fonts (qui peut être bloquée sans dégrader la fonctionnalité).

---

## 2. Modes d'entraînement

| Mode | Volume | Caractéristique |
|---|---|---|
| **Thématique** | 30 questions | Tirage aléatoire dans une activité au choix |
| **Mixte** | 50 questions | Tirage aléatoire dans les 7 activités |
| **Examen blanc** | 70 questions | 10 par activité, chronométré 60 minutes |

Les questions sont mélangées à chaque tirage (algorithme Fisher-Yates), ce qui signifie qu'un même mode lancé deux fois produit des séries différentes. Cela favorise l'apprentissage par répétition espacée.

---

## 3. Conformité au référentiel BTS GPME

Pour chaque activité, j'ai veillé à couvrir les sous-domaines suivants :

**A4.1 - Recherche de clientèle et contact**
- Prospection et qualification (BANT, SONCAS, CAB, CRAC) - 15 Q
- Outils CRM, segmentation (RFM, ABC, scoring) - 12 Q
- Cadre juridique et déontologique (RGPD, Bloctel, opt-in) - 10 Q
- Indicateurs commerciaux (NPS, CSAT, taux de conversion) - 8 Q
- Cycle de vente et fidélisation - 5 Q

**A4.2 - Administration des ventes / Communication interne**
- Documents commerciaux (devis, BC, BL, facture, CGV) - 12 Q
- Outils SI et collaboratifs (CRM, ERP, workflow, EDI) - 10 Q
- Méthodes lean / qualité (Ishikawa, 5 pourquoi, RACI, Gantt) - 12 Q
- Réunion et communication interne (ODJ, CR, note de service) - 8 Q
- Indicateurs opérationnels (lead time, taux d'erreur) - 8 Q

**A4.3 - Administration du personnel** (sans capsule)
- Cycle d'embauche (DPAE, contrats, période d'essai) - 12 Q
- Paie et déclarations sociales (DSN, IJSS, prélèvement à la source) - 10 Q
- Suivi du personnel (congés, arrêts, formation, GPEC, CPF) - 12 Q
- Droit du travail (durée, conventions collectives, CSE) - 10 Q
- RGPD RH et confidentialité - 6 Q

**A4.4 - Communication institutionnelle**
- Cibles et formes de communication - 8 Q
- Communication de crise et e-réputation - 12 Q
- Documents (note interne, communiqué, post RS) - 10 Q
- Relations presse (RP, kit média, communiqué) - 8 Q
- Mécénat, sponsoring, marque-employeur - 6 Q
- Communication interne (top-down, bottom-up) - 6 Q

**A4.5 - Analyse de l'activité**
- Coûts variables / fixes, MCV unitaire et globale - 10 Q
- Seuil de rentabilité (valeur, quantité, point mort) - 12 Q
- Marge et indice de sécurité - 6 Q
- Budget de trésorerie - 10 Q
- Analyse de sensibilité (effet ciseau, prix, coûts) - 6 Q
- Cas chiffré récurrent : prix 28 € / CV 12,50 € / CF 48 000 € (cohérent capsule mercredi matin) - 6 Q

**A4.6 - Diagnostic financier**
- Bilan fonctionnel (FRNG, BFR, trésorerie nette) - 10 Q
- SIG (VA, EBE, CAF) - 10 Q
- Ratios (autonomie, endettement, rentabilité, liquidité) - 10 Q
- Plan de financement et choix d'investissement (VAN, TIR) - 10 Q
- Délais (clients, fournisseurs, rotation stocks) et BFR - 10 Q

**A4.7 - Tableaux de bord et reporting** (sans capsule)
- Définition KPI, SMART, indicateurs avancés/retardés - 10 Q
- Construction TDB (objectif, écart, code-feu, alertes) - 10 Q
- Outils tableur (Excel : RECHERCHEV, TCD, MFC, sparkline) - 10 Q
- Reporting (structure, fréquence, commentaire qualitatif) - 8 Q
- KPI métier (commercial, financier, RH, logistique) - 12 Q

---

## 4. POINT DE VIGILANCE - Deux corrections successives

### 4.1 Rééquilibrage de la position des bonnes réponses

**Auto-critique préventive (Mécanisme 1) :**

À l'issue de l'injection initiale, j'ai détecté un **biais pédagogique majeur** dans la distribution des bonnes réponses :
- Avant correction : 89% des bonnes réponses étaient en position 0 (1ère option), 11% en position 1, 0% en position 2.
- Cause : par habitude, j'ai tendance à formuler la bonne réponse en premier lors de la rédaction.
- Risque : une étudiante avec une simple intuition stratégique ("la première option qui semble la plus complète") aurait obtenu un taux de réussite artificiellement élevé sans maîtriser la matière.

**Action corrective :**

J'ai exécuté un script de rééquilibrage déterministe (`reequilibrage-qcm.py`) qui :
1. Parse les 350 questions
2. Calcule une nouvelle position cible par hashing de l'ID : `(id × 7 + 13) % 3`
3. Permute l'option correcte avec celle en position cible si différente
4. Réécrit le fichier

**Distribution après correction :** 117/116/117 (33%/33%/33%), équilibre vérifié aussi par activité.

### 4.2 Correction du vocabulaire TRT

**Signalement de Kévin :**

Le vocabulaire utilisé dans la première version de la banque (questions Q51 à Q53) ne correspondait pas exactement à la fiche de cours CADP étudiée par les étudiantes :

| Terme initial | Vocabulaire CADP officiel |
|---|---|
| "Taux de charge" | **Taux d'engagement** |
| Heures travaillées / heures théoriques | **Charge nette / Temps théorique** |
| (notion absente) | **Charge nette = charge estimée + 15%** (pauses, aléas, vitesse) |
| "Surcharge si > 100%" uniquement | Trois seuils : < 95% non saturé / 95-99% saturé / > 100% surchargé |
| (notion absente) | **Feuille d'analyse des tâches** (étape préalable au TRT) |
| (notion absente) | **Tableau des compétences** (analyse qualitative) |

**Actions correctives :**

1. **Reformulation de 3 questions** :
   - Q51 : objectif TRT précisé selon le cours (analyse de la pertinence en tenant compte des compétences et de la charge)
   - Q52 : "taux de charge" → "taux d'engagement" + formule charge nette / temps théorique
   - Q53 : seuils CADP officiels (95%, 95-99%, >100%)

2. **Remplacement de 4 questions doublons** par 4 nouvelles questions sur les notions du cours absentes :
   - Q81 (ancien tableau de bord op., doublon A4.7) → **charge nette = charge estimée + 15%**
   - Q88 (ancien procédure vs instruction) → **feuille d'analyse des tâches**
   - Q95 (ancien SWOT, doublon A4.5/A4.6) → **tableau des compétences**
   - Q96 (ancien KPI, doublon A4.7) → **seuils du taux d'engagement (95-99%)**

**Vérifications post-correction :**

- 350 questions confirmées, 50 par activité maintenues
- Équilibre 33%/33%/33% préservé (117/116/117)
- Équilibre A4.2 spécifique : 16/17/17 sur 50
- Vocabulaire correct : "taux de charge" éliminé (0 occurrence), "taux d'engagement" présent (4 occurrences)
- Notions du cours intégrées : "charge nette" (2 occ.), "feuille d'analyse" (3 occ.), "tableau des compétences" (2 occ.)

### 4.3 Conséquence sur la capsule lundi

**Alerte signalée à Kévin :**

La capsule `capsule-lundi-tableau-repartition.html` utilise actuellement le vocabulaire "taux d'occupation" (qui n'est ni le terme CADP "taux d'engagement", ni le faux "taux de charge"). Elle ne mentionne ni la charge nette, ni la feuille d'analyse des tâches, ni le tableau des compétences, ni les seuils 95%/99%/100%.

Décision attendue de Kévin : corriger la capsule lundi avant le push GitHub Pages, ou pousser en l'état et faire la correction dans une mise à jour ultérieure.

---

## 5. Limites assumées

### 5.1 Format limité à 3 options

Toutes les questions ont 3 propositions de réponse. Pour des QCM véritablement discriminants en examen, 4 propositions sont parfois préférables (réduit la probabilité de réussite par hasard de 33% à 25%). Mais 3 options accélèrent l'entraînement et limitent la fatigue cognitive sur 70 questions consécutives en mode examen blanc. Choix assumé pour la révision.

### 5.2 Pas de questions à plusieurs bonnes réponses

J'ai opté pour des QCM à réponse unique. Cela facilite l'auto-correction et la lecture des résultats. Les questions à choix multiples (cocher toutes les bonnes réponses) sont absentes. Un futur enrichissement possible.

### 5.3 Activités non couvertes par capsule

Les 50 questions sur A4.3 et A4.7 ont été produites directement à partir du référentiel officiel et de la connaissance générale du domaine, sans le contexte narratif Olivier & Filles. Elles sont conformes au référentiel mais plus académiques que les questions des activités traitées en capsule (qui peuvent ré-exploiter les calculs et personnages des cas pratiques).

### 5.4 Rotation des positions = même test à plusieurs reprises

Comme les questions sont tirées aléatoirement, une étudiante qui répète plusieurs fois le même mode tombera occasionnellement sur les mêmes questions. Le pool est de 50 questions par activité, ce qui limite mais n'élimine pas ce phénomène. Recommandation : privilégier le mode mixte ou examen blanc après plusieurs sessions thématiques.

### 5.5 Pas de différenciation par niveau de difficulté

Les questions sont à difficulté homogène, plutôt orientée "compréhension du cours" (niveau requis pour 70-80% des questions de l'épreuve écrite type). Quelques questions sont plus exigeantes (calculs A4.5, ratios A4.6), mais sans graduation explicite. Une future amélioration pourrait introduire un champ `niveau` (1=basique, 2=intermédiaire, 3=avancé).

---

## 6. Workflow de validation - rappel méthodologique

**Action 1 - Test ergonomique (15 min recommandées)**

1. Identification : nom + prénom, vérifier que le bandeau s'affiche
2. Mode thématique : choisir A4.5, lancer 30 questions, vérifier l'aléatoire (relancer une 2e fois → questions différentes)
3. Compléter le quiz, vérifier l'écran de résultats : score global + détail par activité + revue détaillée
4. Mode mixte : 50 questions toutes activités confondues
5. Mode examen blanc : démarrer, vérifier que le timer de 60 minutes apparaît bien, qu'il devient orange en dessous de 10 min et rouge en dessous d'1 min. Faire au moins 5 questions et terminer manuellement.
6. Vérifier l'historique en bas de page (10 derniers résultats)
7. Tester le mailto récap : il doit inclure scores, mode, et liste des questions ratées

**Action 2 - Lecture de l'audit (5 min)**

Ouvrir cette note et vérifier particulièrement :
- §4 sur le rééquilibrage post-injection (transparence sur le biais détecté et corrigé)
- §5 sur les limites assumées

**Action 3 - Décision**

- **GO push** : on enchaîne avec le push GitHub des 5 capsules + banque QCM
- **Ajustement** : tu me dis quoi modifier (ajouter une 4e option, ajouter un niveau de difficulté, etc.)

---

## 7. Conclusion

La banque de 350 QCM couvre l'intégralité du référentiel A4.1 à A4.7, avec une répartition équilibrée des bonnes réponses (33%/33%/33%) après correction d'un biais pédagogique détecté en auto-critique. Les trois modes (thématique, mixte, examen blanc) couvrent les besoins de révision ciblée comme d'entraînement à l'épreuve. Le fichier est autonome, persistant et compatible avec la chaîne CADP existante.

**Statut** : prête à être validée avant push GitHub Pages.

---

*Note produite le 10 mai 2026 par Claude pour Kévin Vidard - CADP*
*Méthodologie CADP-Claude v1.0 - Garde-fous n°1 (auto-critique) et n°4 (audit final pre-commit)*
