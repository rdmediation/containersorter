# Container Sorter - Optimiseur Génétique 🧬

Un algorithme génétique avancé pour l'assemblage optimal de containers en groupes homogènes de 4 unités, optimisant simultanément deux variables (V1 et V2).

## 🎯 Description

Cette application web utilise un algorithme génétique pour résoudre le problème d'optimisation combinatoire complexe consistant à regrouper des containers en groupes de 4, où chaque groupe doit respecter des objectifs de moyenne pour deux variables V1 et V2 avec des tolérances définies.

## 🚀 Fonctionnalités

- **Algorithme Génétique Multi-Objectif**: Optimisation simultanée de deux variables V1 et V2
- **Interface Web Interactive**: Visualisation 3D des containers avec des cubes animés
- **Paramètres Configurables**: 
  - Objectifs V1/V2 et tolérances personnalisables
  - Paramètres de l'algorithme génétique (population, mutation, croisement, etc.)
- **Import/Export CSV**: Chargement de données personnalisées et export des résultats
- **Métriques en Temps Réel**: 
  - Score de fitness
  - Taux de convergence
  - Index de diversité
  - Nombre de groupes conformes
- **Visualisation des Résultats**: Affichage des groupes optimisés avec statistiques détaillées

## 📊 Paramètres d'Optimisation

### Objectifs
- **V1 Cible**: 45-55 (défaut: 50.0)
- **V2 Cible**: 20-30 (défaut: 25.0)
- **Tolérances**: Écarts acceptables pour V1 (±2.0) et V2 (±1.5)

### Algorithme Génétique
- **Taille Population**: 50-500 (défaut: 150)
- **Taux Mutation**: 1-50% (défaut: 15%)
- **Max Générations**: 50-1000 (défaut: 300)
- **Taux Élitisme**: 1-30% (défaut: 10%)
- **Taille Tournoi**: 2-10 (défaut: 5)
- **Taux Croisement**: 50-100% (défaut: 80%)

## 📋 Format des Données

### Fichier CSV d'Entrée
```csv
id,v1,v2
1,47.23,22.45
2,52.11,26.78
3,48.67,24.32
...
```

### Fichier CSV de Sortie
```csv
groupe_id,container_id,v1,v2,mean_v1,mean_v2,variance_v1,variance_v2,v1_conforme,v2_conforme
1,0,47.23,22.45,49.21,24.12,2.34,1.87,true,true
1,1,52.11,26.78,49.21,24.12,2.34,1.87,true,true
...
```

## 🛠️ Utilisation

1. **Ouvrir l'application**: Ouvrez `index.html` dans un navigateur web
2. **Configurer les objectifs**: Définissez V1/V2 cibles et tolérances
3. **Paramétrer l'algorithme**: Ajustez les paramètres génétiques selon vos besoins
4. **Charger les données**: 
   - Utilisez "Générer Containers" pour des données aléatoires (64 containers)
   - Ou chargez un fichier CSV personnalisé
5. **Optimiser**: Cliquez sur "Optimiser" pour lancer l'algorithme
6. **Analyser les résultats**: Consultez les groupes optimisés et leurs statistiques
7. **Exporter**: Téléchargez les résultats au format CSV

## 🧮 Algorithme

L'optimiseur utilise un algorithme génétique avec les opérateurs suivants:

- **Sélection**: Tournoi
- **Croisement**: Point de coupure avec réparation
- **Mutation**: 3 types (échange, mélange, permutation de groupes)
- **Élitisme**: Conservation des meilleures solutions
- **Fonction de Fitness**: Multi-critères avec bonus pour conformité

### Critères d'Évaluation
- Écart par rapport aux objectifs V1/V2
- Variance intra-groupe
- Nombre de groupes conformes
- Bonus de convergence

## 🎨 Interface

- **Cubes 3D Animés**: Chaque container est représenté par un cube coloré selon ses valeurs V1/V2
- **Statistiques Temps Réel**: Tableau de bord avec métriques d'optimisation
- **Barre de Progression**: Suivi de l'évolution de l'algorithme
- **Groupes Optimisés**: Affichage détaillé des solutions avec indicateurs de conformité

## 🔧 Technologies

- **Frontend**: HTML5, CSS3, JavaScript (ES6+)
- **Bibliothèques**: jQuery 3.7.0
- **Algorithme**: Génétique personnalisé
- **Visualisation**: CSS3 Transforms, Animations

## 📈 Performance

L'application est optimisée pour traiter:
- Jusqu'à 500 containers simultanément
- Populations d'algorithmes génétiques jusqu'à 500 individus
- Convergence typique en 100-300 générations

## ⚠️ Avertissement

**Code expérimental R&D Mediation 2025 - Ne pas utiliser en production**

## 📝 Exemple d'Utilisation

1. Charger 200 containers depuis `containers-example.csv`
2. Définir objectifs V1=50±2, V2=25±1.5
3. Lancer l'optimisation avec population=150, 300 générations
4. Obtenir ~50 groupes de 4 containers optimisés
5. Exporter les résultats pour analyse ultérieure

Le système vise à maximiser le nombre de groupes respectant simultanément les deux contraintes V1 et V2 tout en minimisant la variance intra-groupe.