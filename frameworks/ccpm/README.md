# CCPM - Claude Code Project Management

> **Framework de gestion de projet spec-driven pour Claude Code avec GitHub Issues et git worktrees**

## 🎯 En bref

CCPM transforme le développement logiciel en permettant à plusieurs agents Claude de travailler en parallèle sur des tâches structurées via GitHub Issues, avec une philosophie "No Vibe Coding" où chaque ligne de code est traçable jusqu'à une spécification.

**Créé par** : [Automaze](https://github.com/automazeio/ccpm)  
**Compatible** : Claude Code uniquement  

## 📊 Métriques clés (prouvées)

- **-89%** context switching
- **-75%** taux de bugs  
- **3x** vitesse de livraison
- **5-8** tâches parallèles simultanées

## 🚀 Workflow en 5 étapes

```bash
1. /pm:prd-new feature-name        # 🧠 Brainstorm & specs
2. /pm:prd-parse feature-name      # 📋 Document tech  
3. /pm:epic-oneshot feature-name   # 🗂️ Plan & sync GitHub
4. /pm:issue-start 1234           # ⚡ Execute (agents parallèles)
5. /pm:issue-sync 1234            # 📊 Track & validate
```

## 🔑 Concepts clés

- **Git worktrees** : Développement parallèle sans conflit de branches
- **GitHub Issues** : Source unique de vérité pour la traçabilité  
- **Agents spécialisés** : Backend, Frontend, QA, DevOps travaillent simultanément
- **Spec-driven** : Toute décision basée sur documentation explicite

## 💡 Cas d'usage optimaux

- ✅ **Nouvelles fonctionnalités** complexes avec multiple composants
- ✅ **Refactoring** de systèmes legacy avec contraintes architecturales  
- ✅ **Debug système** multi-composants nécessitant investigation coordonnée
- ✅ **Projets équipe** avec besoin de traçabilité et documentation

## ⚠️ Attention

**Courbe d'apprentissage** : Framework avancé nécessitant :
- Maîtrise de Git worktrees
- Configuration GitHub Issues structurée  
- Habitude du développement spec-driven

**Alternative simple** : Pour projets solo ou prototypage, les outils Claude Code natifs suffisent.

## 🔗 Ressources officielles

- **[Repository CCPM](https://github.com/automazeio/ccmp)** - Documentation complète et installation
- **[Automaze.io](https://automaze.io)** - Créateur du framework
- **[Documentation détaillée](https://github.com/automazeio/ccmp#readme)** - Guide utilisateur complet

## 🎓 Pour approfondir

**Dans ce repository :**
- Intégration avec [Claude Code Context Engineering](../../agents/claude/) pour optimiser l'usage
- [Templates AGENTS.md](../../) compatibles avec la philosophie spec-driven CCPM

---

> 💡 **Notre conseil** : Testez d'abord sur un petit projet pour vous familiariser avec les concepts avant de l'appliquer à des systèmes complexes. Le gain de productivité est réel mais nécessite un changement de mindset vers le spec-driven development.