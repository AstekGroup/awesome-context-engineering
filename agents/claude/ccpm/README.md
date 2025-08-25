# CCPM - Claude Code Project Management 🚀

> Système de gestion de projet pour Claude Code utilisant GitHub Issues et Git worktrees pour l'exécution parallèle d'agents IA

CCPM (Claude Code Project Management) est un framework révolutionnaire qui transforme le développement logiciel en permettant une collaboration spec-driven avec des agents IA multiples. Développé par [Automaze](https://github.com/automazeio/ccpm), il optimise la productivité des développeurs et élimine le "Vibe Coding".

## 🎯 Philosophie "No Vibe Coding"

**Principe fondamental :** Chaque ligne de code doit pouvoir être tracée jusqu'à une spécification claire.

- **Spec-driven Development** : Toutes les décisions basées sur des spécifications documentées
- **Traçabilité complète** : Du besoin produit au code final
- **Collaboration transparente** : Utilisation native de GitHub comme plateforme centrale
- **Exécution parallèle** : Plusieurs agents Claude travaillent simultanément sur différentes tâches

## 📊 Métriques de performance

| Métrique | Amélioration |
|----------|-------------|
| **Context switching** | -89% |
| **Tâches parallèles** | 5-8 simultanées |
| **Réduction des bugs** | -75% |
| **Vitesse de livraison** | 3x plus rapide |

## 🏗️ Architecture du workflow

```mermaid
graph LR
    A[🧠 Brainstorm] --> B[📋 Document]
    B --> C[🗂️ Plan]
    C --> D[⚡ Execute]
    D --> E[📊 Track]
    E --> D
```

### Phases du workflow

1. **Brainstorm** 🧠 : Idéation et définition des besoins
2. **Document** 📋 : Création des PRD (Product Requirements Document)
3. **Plan** 🗂️ : Décomposition en epics et tâches techniques
4. **Execute** ⚡ : Développement parallèle par agents spécialisés
5. **Track** 📊 : Suivi et synchronisation GitHub

## 🛠️ Installation et configuration

### Prérequis
- Dépôt GitHub configuré
- Accès à Claude Code
- Git avec support des worktrees

### Étapes d'installation

1. **Cloner CCPM dans votre projet**
```bash
git clone https://github.com/automazeio/ccpm.git .ccpm
```

2. **Initialiser le framework**
```bash
# Dans Claude Code
/pm:init
```

3. **Configuration GitHub**
```bash
# Authentification GitHub (si nécessaire)
gh auth login
```

4. **Structure de répertoire créée**
```
votre-projet/
├── .claude/          # Configuration CCPM
├── .ccpm/            # Framework CCPM  
├── docs/
│   ├── prds/         # Product Requirements Documents
│   └── epics/        # Epics techniques
└── src/              # Code source
```

## 🎮 Commandes CCPM

### 📋 Gestion des PRD (Product Requirements Document)

#### Créer un nouveau PRD
```bash
/pm:prd-new memory-system
```
- Génère un PRD structuré pour la fonctionnalité
- Template avec sections : Objectif, Spécifications, Critères d'acceptance

#### Parser un PRD en epic technique  
```bash
/pm:prd-parse memory-system
```
- Convertit les exigences produit en spécifications techniques
- Génère l'architecture et les dépendances

#### Lister les PRD existants
```bash
/pm:prd-list
```

### 🗂️ Gestion des Epics

#### Décomposer un epic en tâches
```bash
/pm:epic-decompose memory-system
```
- Découpe l'epic en tâches atomiques
- Estime la complexité et les dépendances
- Génère les User Stories techniques

#### Synchroniser avec GitHub Issues
```bash
/pm:epic-sync memory-system
```
- Crée les issues GitHub automatiquement  
- Organise les labels et milestones
- Établit les relations entre tâches

#### Décomposition + Synchronisation (oneshot)
```bash
/pm:epic-oneshot memory-system
```
- Combine `epic-decompose` et `epic-sync`
- Workflow complet en une commande

### 🎯 Gestion des Issues

#### Démarrer le travail sur une issue
```bash
/pm:issue-start 1235
```
- Crée un git worktree dédié
- Configure le contexte de développement
- Assigne l'agent spécialisé

#### Synchroniser les progrès
```bash
/pm:issue-sync 1235
```
- Met à jour l'issue GitHub avec les progrès
- Synchronise le code et les commentaires
- Maintient la traçabilité

#### Clôturer une issue
```bash
/pm:issue-close 1235
```
- Finalise l'implémentation
- Merge le worktree
- Marque l'issue comme terminée

### 📊 Suivi et reporting

#### État du projet
```bash
/pm:status
```

#### Métriques de productivité
```bash
/pm:metrics
```

## 🧠 Concepts techniques avancés

### Git Worktrees
CCPM utilise les **git worktrees** pour permettre le travail parallèle :

```bash
# Automatiquement créé par /pm:issue-start
git worktree add ../workspaces/issue-1235 feature/memory-system
```

**Avantages :**
- Chaque agent travaille dans un environnement isolé
- Pas de conflit de branche
- Context switching quasi-instantané
- Développement parallèle réel

### GitHub Issues comme Source de Vérité
- **Single Source of Truth** : Toute l'information centralisée
- **Traçabilité bidirectionnelle** : Code ↔ Spécifications
- **Collaboration native** : Comments, reviews, approvals
- **Automation** : Hooks et workflows automatisés

### Agents Spécialisés
CCPM orchestre différents types d'agents Claude :

| Agent | Spécialisation | Contexte |
|-------|---------------|----------|
| **Architect** | Design système, patterns | Architecture globale |
| **Frontend** | UI/UX, composants React | Interface utilisateur |
| **Backend** | API, base de données | Services et données |  
| **QA** | Tests, validation | Qualité et fiabilité |
| **DevOps** | CI/CD, déploiement | Infrastructure |

## 💡 Cas d'usage recommandés

### 🚀 Développement de nouvelles fonctionnalités

**Scénario :** Implémenter un système de gestion mémoire

1. **Création du PRD**
```bash
/pm:prd-new memory-system
```

2. **Planification technique**
```bash
/pm:prd-parse memory-system
/pm:epic-oneshot memory-system  
```

3. **Développement parallèle**
```bash
# Agent 1 : Architecture
/pm:issue-start 1235  # Core memory manager

# Agent 2 : Frontend  
/pm:issue-start 1236  # Memory usage dashboard

# Agent 3 : Tests
/pm:issue-start 1237  # Integration tests
```

### 🔧 Refactoring de code legacy

**Scénario :** Moderniser une base de code monolithique

```bash
# 1. Audit et documentation
/pm:prd-new legacy-refactoring

# 2. Stratégie de migration
/pm:epic-decompose legacy-refactoring

# 3. Migration par modules
/pm:issue-start 1240  # User module
/pm:issue-start 1241  # Payment module  
/pm:issue-start 1242  # Notification module
```

### 🐛 Résolution de bugs complexes

**Scénario :** Bug système affectant plusieurs composants

```bash
# 1. Investigation
/pm:prd-new bug-investigation-auth-timeout

# 2. Plan de résolution
/pm:epic-oneshot bug-investigation-auth-timeout

# 3. Correction coordonnée
/pm:issue-start 1250  # Frontend timeout handling
/pm:issue-start 1251  # Backend session management
/pm:issue-start 1252  # Infrastructure monitoring
```

## 📈 Workflow optimal

### Phase 1: Brainstorm et spécifications
```bash
# Créer et affiner les spécifications
/pm:prd-new nouvelle-fonctionnalité
/pm:prd-edit nouvelle-fonctionnalité
```

### Phase 2: Planification technique  
```bash
# Convertir en plan d'implémentation
/pm:prd-parse nouvelle-fonctionnalité
/pm:epic-decompose nouvelle-fonctionnalité
```

### Phase 3: Synchronisation GitHub
```bash
# Créer les issues et organiser le board
/pm:epic-sync nouvelle-fonctionnalité
```

### Phase 4: Exécution parallèle
```bash
# Démarrer le développement sur plusieurs fronts
/pm:issue-start 1001  # Backend API
/pm:issue-start 1002  # Frontend Components  
/pm:issue-start 1003  # Database Schema
/pm:issue-start 1004  # Tests Suite
```

### Phase 5: Suivi et intégration
```bash
# Synchroniser régulièrement
/pm:issue-sync 1001
/pm:issue-sync 1002
/pm:status
```

## 🎯 Avantages clés

### ✅ Pour les développeurs
- **Réduction du context switching** : 89% de temps gagné
- **Clarté des objectifs** : Chaque tâche est spec-driven
- **Travail parallèle** : 5-8 tâches simultanées
- **Traçabilité complète** : De l'idée au code déployé

### ✅ Pour les équipes
- **Collaboration transparente** : GitHub comme hub central  
- **Réduction des bugs** : 75% grâce aux spécifications claires
- **Livraison accélérée** : 3x plus rapide qu'un workflow traditionnel
- **Onboarding simplifié** : Documentation auto-générée

### ✅ Pour les projets
- **Maintenance facilitée** : Code documenté et tracé
- **Évolutivité** : Architecture claire et modulaire
- **Qualité constante** : Standards appliqués automatiquement
- **ROI mesurable** : Métriques de productivité intégrées

## 🔧 Configuration avancée

### Personnalisation des agents
```yaml
# .claude/ccpm-config.yml
agents:
  architect:
    model: "claude-3.5-sonnet"
    context_size: 200000
    specialization: ["system-design", "architecture-patterns"]
  
  frontend:
    model: "claude-3.5-sonnet"  
    context_size: 100000
    specialization: ["react", "typescript", "ui-ux"]
```

### Templates de PRD personnalisés
```markdown
# docs/templates/prd-template.md
## 🎯 Objectif
[Description de la fonctionnalité]

## 📋 Spécifications  
[Exigences détaillées]

## ✅ Critères d'acceptance
[Conditions de validation]

## 🏗️ Contraintes techniques
[Limitations et dépendances]
```

### Hooks et automatisation
```bash
# .github/workflows/ccpm-sync.yml
name: CCPM Sync
on:
  issues: [opened, edited, closed]
  
jobs:
  sync-ccpm:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Sync CCPM
        run: /pm:sync-all
```

## 🚀 Prochaines étapes

1. **[Installation rapide](./installation.md)** - Guide détaillé d'installation
2. **[Exemples pratiques](./examples/)** - Cas d'usage réels documentés  
3. **[Templates](./templates/)** - PRD et epic templates personnalisables
4. **[Intégration CI/CD](./cicd-integration.md)** - Automatisation des workflows
5. **[Migration](./migration-guide.md)** - Adopter CCPM sur projets existants

## 🔗 Ressources et communauté

### Documentation officielle
- **[Repository CCPM](https://github.com/automazeio/ccpm)** - Code source et documentation
- **[Automaze.io](https://automaze.io)** - Créateur du framework

### Communauté
- **[Discussions GitHub](https://github.com/automazeio/ccpm/discussions)** - Questions et retours d'expérience
- **[Issues](https://github.com/automazeio/ccpm/issues)** - Bugs et demandes de fonctionnalités

---

> 💡 **Conseil :** Commencez par un petit projet pour vous familiariser avec les concepts CCPM avant de l'appliquer à des projets plus complexes. La courbe d'apprentissage est rapide, mais l'adoption progressive garantit une meilleure maîtrise du framework.