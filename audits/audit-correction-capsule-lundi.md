# Audit de correction - Capsule lundi (TRT)

**Capsule** : Tableau de Répartition des Tâches (A4.2)
**Fichier** : `capsule-lundi-tableau-repartition.html`
**Date de correction** : 10 mai 2026
**Motif** : alignement sur le vocabulaire CADP officiel signalé par Kévin

---

## 1. Pourquoi cette correction

La première version de la capsule lundi utilisait un vocabulaire imprécis ne correspondant pas à la fiche de cours CADP étudiée par les étudiantes en classe. La banque QCM ayant été corrigée pour utiliser le vocabulaire officiel, il était essentiel d'aligner également la capsule lundi pour éviter toute dissonance pédagogique.

---

## 2. Modifications apportées

### 2.1 Vocabulaire (changements terminologiques)

| Avant | Après |
|---|---|
| Taux d'occupation | **Taux d'engagement** |
| Heures travaillées | **Charge estimée** (heures déclarées) puis **charge nette** (× 1,15) |
| Temps théorique 140h | **Temps théorique 151,67h** (35h × 52 semaines / 12 mois) |
| Sous-occupation | **Non saturé** (vocabulaire CADP) |

### 2.2 Notions ajoutées (absentes de la version initiale)

- **Feuille d'analyse des tâches** : étape préalable au TRT, recueillant pour chaque salarié liste des tâches, documents associés et temps consacré par semaine
- **Charge estimée vs charge nette** : la charge nette correspond à la charge estimée majorée de 15% pour intégrer les temps non productifs (pauses, aléas, vitesse d'exécution)
- **Tableau des compétences** : grille qualitative croisant agents et tâches, complémentaire de l'analyse quantitative
- **Méthode CADP en 4 étapes** : feuille d'analyse → élaboration TRT → analyse quantitative + tableau compétences → nouveau TRT
- **Trois seuils du taux d'engagement** : <95% non saturé / 95-99% saturé / >100% surchargé

### 2.3 Recalculs des données chiffrées

L'application stricte de la méthode CADP (charge nette × 1,15 / temps théorique 151,67h) imposait de revoir les chiffres pour conserver une cohérence pédagogique avec les seuils CADP. Les nouveaux chiffres ont été calibrés pour préserver les statuts narratifs (Théa surchargée, Sophie non saturée modérément, Léa très non saturée) :

| Personne | Charge estimée | Charge nette | Taux d'engagement | Statut CADP |
|---|---|---|---|---|
| Théa Bonnefoy | 145h | 166,75h | 110% | Surchargée (>100%) |
| Sophie Vasquez | 115h | 132,25h | 87% | Non saturée (<95%) |
| Léa Dupré | 73h | 83,95h | 55% | Non saturée (<95%) |
| **Total** | **333h** | **382,95h** | - | - |

### 2.4 Modifications des heures par tâche (pour aboutir aux nouveaux totaux)

Six tâches sur 18 ont été ajustées (-21h pour Théa, -9h pour Sophie, -1h pour Léa) :

| Tâche | Avant | Après | Variation |
|---|---|---|---|
| 1 - Saisie factures fournisseurs (Théa) | 36h | 32h | -4h |
| 4 - Suivi règlements clients (Théa) | 22h | 18h | -4h |
| 11 - Archivage (Théa) | 8h | 5h | -3h |
| 13 - Préparation devis (Sophie) | 32h | 28h | -4h |
| 14 - Suivi commandes (Sophie) | 28h | 25h | -3h |
| 15 - Réponse demandes prospects (Sophie) | 24h | 22h | -2h |
| 17 - Gestion agenda (Léa) | 36h | 35h | -1h |

### 2.5 Recalcul des 3 propositions de réorganisation

Les 3 propositions du corrigé exo 3.4 ont été recalculées pour rester cohérentes :

| Étape | Théa | Sophie | Léa |
|---|---|---|---|
| État initial | 110% (surchargée) | 87% | 55% |
| Après prop 1 (suppression doublon tâche 9) | 99% (saturée) | 87% | 55% |
| Après prop 1 + 2 (transfert archivage + mails Théa→Léa) | 89% | 87% | 65% |
| Après prop 1 + 2 + 3 (rationalisation tâche 10) | 83% | 81% | 74% |

---

## 3. Sections modifiées du fichier

| Section | Modifications |
|---|---|
| Cadrage théorique (cours) | Refonte complète : 4 étapes méthode CADP, lexique étendu, encadré seuils |
| Tableau de répartition (tableau visuel) | Pied de tableau étendu avec 3 lignes : charges estimées, charges nettes, taux d'engagement |
| Données JS (TABLEAU_DONNEES) | 7 valeurs ajustées sur 18 tâches (voir §2.4) |
| Exercice 3.1 (saisie totaux) | Intitulé reformulé "charges estimées", nouveaux totaux 145/115/73 |
| Exercice 3.2 (calcul taux) | Refonte : formule en deux étapes (charge nette puis taux d'engagement), temps théorique 151,67h |
| Corrigé exo 3.2 (détail) | 3 erreurs fréquentes mises à jour (oubli majoration, mauvais temps théorique, arrondi prématuré) |
| Corrigé exo 3.4 (3 propositions) | Recalcul complet des 3 propositions cumulatives |
| Note finale (synthèse production) | Constats reformulés avec vocabulaire CADP, ajout référence tableau des compétences |
| Synthèse phase 5 (5 cartes + lexique) | Refonte des 5 cartes + lexique étendu à 12 entrées (vs 7 avant) |
| QCM Phase 2 (Q5 et Q6) | Reformulation taux d'engagement + ajout question sur seuils CADP |
| QCM Phase 3 (Q1 et Q4) | Mise à jour chiffres et vocabulaire |
| Libellés JS (score + mailto) | "Taux d'occupation" → "Taux d'engagement" |

---

## 4. Vérifications post-correction

| Vérification | Résultat |
|---|---|
| Balises HTML/JS équilibrées (DOCTYPE, html, body, style, script) | OK |
| Tags `<div>`, `<section>`, `<button>`, `<textarea>`, `<table>` équilibrés | OK |
| "Taux d'occupation" résiduel | 0 occurrence (éliminé) |
| "Taux d'engagement" présent | 27 occurrences |
| "Charge nette" présent | 25 occurrences |
| "Charge estimée" présent | 28 occurrences |
| "Feuille d'analyse des tâches" présent | 5 occurrences |
| "Tableau des compétences" présent | 9 occurrences |
| "151,67" présent | 13 occurrences |
| "140 h" / "140 heures" résiduel | 0 occurrence |
| Chiffres anciens (156, 124, 111%, 354) | 0 occurrence |
| Chiffres nouveaux (145, 115, 110%, 87%, 55%, 333) | présents |
| Taille fichier | 94 ko (vs 87 ko version initiale) |

---

## 5. Cohérence avec les autres ressources

### 5.1 Avec la banque QCM (corrigée précédemment)

Les 7 questions de la banque QCM sur le TRT (Q51-Q53 reformulées + Q81/88/95/96 nouvelles) utilisent strictement le même vocabulaire CADP. Aucune dissonance.

### 5.2 Avec la capsule mardi PM (incident Hambourg)

La capsule mardi PM mentionne Théa comme étant en situation de surcharge (à raison du temps consacré au reporting et aux tâches comptables). Ce constat narratif reste cohérent : le taux d'engagement de Théa reste supérieur à 100% (110% au lieu de 111%). Pas de modification nécessaire dans la capsule mardi PM.

### 5.3 Avec les autres capsules

Les capsules mardi matin (diagnostic financier), mercredi matin (analyse activité), mercredi PM (communication crise) ne mobilisent pas la méthode TRT et ne sont pas affectées par cette correction.

---

## 6. Conclusion

La capsule lundi est désormais alignée sur le vocabulaire CADP officiel et sur la méthode complète en 4 étapes (feuille d'analyse → TRT → analyse + tableau compétences → nouveau TRT). Les étudiantes retrouveront le même vocabulaire dans la capsule, dans la banque QCM et dans le cours qu'elles ont eu en classe.

**Statut** : prête pour le push GitHub Pages.

---

*Audit produit le 10 mai 2026 par Claude pour Kévin Vidard - CADP*
*Méthodologie CADP-Claude v1.0 - Garde-fou n°4 (audit final pre-commit)*
