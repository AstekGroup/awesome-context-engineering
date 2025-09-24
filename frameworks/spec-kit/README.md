# Spec Kit

**Spec-Driven Development** • Développement piloté par les spécifications • Framework GitHub

## 📋 Vue d'ensemble

Spec Kit est un toolkit innovant pour le **Spec-Driven Development (SDD)**, une méthodologie révolutionnaire qui transforme le développement logiciel en rendant les spécifications exécutables et centrales au processus de développement.

### 🎯 Philosophie Core

- **Développement orienté intention** : Les spécifications définissent le "quoi" avant le "comment"
- **Spécifications exécutables** : Génération automatique d'implémentations fonctionnelles
- **Approche "0-to-1"** : Création de projets complets à partir de spécifications détaillées

## 🏗️ Méthodologie SDD

### Phases de Développement

1. **0-to-1 Development** : Génération de projets depuis zéro
2. **Creative Exploration** : Exploration de multiples approches d'implémentation
3. **Iterative Enhancement** : Modernisation et amélioration des systèmes existants

### Workflow Principal

```
📝 Spécification → 🎯 Plan technique → 📋 Tâches → 💻 Implémentation
```

## 🛠️ Installation et Setup

### Prérequis

- **OS** : Linux/macOS (ou WSL2)
- **Agent IA** : Claude Code, GitHub Copilot, Gemini CLI
- **Python** : 3.11+
- **Package Manager** : uv
- **Version Control** : Git

### Installation

```bash
# Installation de Specify CLI
pip install specify-cli

# Vérification de l'installation
specify --version
```

## 🚀 Usage Pratique

### Commandes Essentielles

| Commande     | Description                                   | Usage                                     |
| ------------ | --------------------------------------------- | ----------------------------------------- |
| `/specify` | Créer une spécification détaillée         | Définition des requirements fonctionnels |
| `/plan`    | Générer un plan d'implémentation technique | Architecture et stratégie technique      |
| `/tasks`   | Décomposer en tâches spécifiques           | Breakdown actionnable                     |

### Exemple de Workflow

```bash
# 1. Initialisation du projet
specify init mon-projet

# 2. Création de la spécification
/specify "Application de gestion de tâches avec authentification JWT"

# 3. Génération du plan technique
/plan

# 4. Décomposition en tâches
/tasks

# 5. Implémentation guidée
specify implement
```

## 🎯 Objectifs Expérimentaux

- **Indépendance technologique** : Support multi-stack
- **Contraintes enterprise** : Intégration dans des environnements complexes
- **Développement user-centric** : Focus sur l'intention utilisateur
- **Processus créatif et itératif** : Innovation par l'expérimentation

## 💡 Différenciateurs Clés

### vs Développement Traditionnel

| Traditionnel          | Spec-Driven                  |
| --------------------- | ---------------------------- |
| Code → Documentation | Spécification → Code       |
| Documentation jetable | Spécifications exécutables |
| "Comment" en premier  | "Quoi" en premier            |
| Refactoring manuel    | Régénération automatique  |

### Avantages

- ✅ **Simplicité :** Framework léger, pouvant être opéré par une seule personne
- **✅ Qualité supérieure** : Spécifications comme source de vérité
- ✅ **Vitesse de développement** : Génération automatique d'implémentations
- ✅ **Cohérence architecturale** : Plans techniques validés
- ✅ **Maintenance simplifiée** : Modifications par mise à jour des specs

## 🧪 Cas d'Usage

### 1. Prototypage Rapide

```
Spécification → MVP fonctionnel en heures
```

### 2. Modernisation Legacy

```
Documentation existante → Spécifications → Nouvelle implémentation
```

### 3. Exploration Créative

```
Multiple specs → Comparaison d'approches → Sélection optimale
```

## 🔗 Intégration avec les Agents IA

### Claude Code

- Utilisation native des commandes `/specify`, `/plan`, `/tasks`
- Génération de code optimisée pour les patterns Claude

### GitHub Copilot

- Spécifications comme contexte pour les suggestions
- Implémentation assistée par l'IA

### Gemini CLI

- Analyse de spécifications complexes
- Génération de plans multi-composants

## 📊 Métriques de Succès

- **Temps de développement** : Réduction de 40-60%
- **Qualité du code** : Amélioration mesurable par les tests automatisés
- **Maintenabilité** : Spécifications comme documentation vivante
- **Innovation** : Exploration rapide de multiples solutions

## 🚧 Statut 

**Statut** : Expérimental (GitHub)
**Licence** : MIT
**Mainteneur** : GitHub Inc.

## 🔧 Ressources et Support

- **Repository** : [github.com/github/spec-kit](https://github.com/github/spec-kit)
- **Documentation** : Auto-déployée sur GitHub Pages
- **Issues** : Support communautaire sur GitHub

## 📝 Notes d'Implémentation

### Pour les Équipes

- **Formation** : Investment initial en méthodologie SDD
- **Outillage** : Configuration des agents IA et environnements
- **Processus** : Adaptation des workflows existants

### Bonnes Pratiques

- Spécifications détaillées et non-ambiguës
- Validation des plans avant implémentation
- Itérations courtes avec feedback constant
- Tests automatisés pour valider les spécifications

---

*Framework ajouté au repository Awesome Context Engineering - Focus sur l'innovation en développement piloté par les spécifications*
