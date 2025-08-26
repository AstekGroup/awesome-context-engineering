# Claude Code - Context Engineering Guide 🎯

> Guide complet pour maîtriser le Context Engineering avec Claude Code CLI et extension VS Code

Claude Code d'Anthropic est un agent de développement disponible en CLI et extension VS Code. Il se distingue par ses capacités de raisonnement avancé, sa fenêtre de contexte massive, et ses outils de Context Engineering sophistiqués.

## 🚀 Démarrage rapide

**Installation et premier usage :**
```bash
# Installation CLI
npm install -g @anthropic-ai/claude-code

# Initialisation projet (génère CLAUDE.md automatiquement)
claude /init

# Démarrage session interactive
claude
```

**Documentation officielle** → [docs.anthropic.com/claude-code](https://docs.anthropic.com/en/docs/claude-code)

---

## 🛠️ Outils officiels de Context Engineering

### 1. Système CLAUDE.md hiérarchique ⭐

Claude Code utilise des fichiers `CLAUDE.md` comme mémoire persistante, chargés automatiquement selon une hiérarchie intelligente :

```
~/.claude/CLAUDE.md              # Règles utilisateur globales
/projet/CLAUDE.md                # Règles spécifiques au projet  
/projet/src/CLAUDE.md            # Règles spécifiques au module
```

**Fonctionnalités clés :**
- **Hiérarchie intelligente** : Global → Projet → Sous-dossier
- **Auto-génération** : `/init` détecte et reprend les règles existantes d'autres agents
- **Import dynamique** : Syntaxe `@chemin/fichier` pour inclure du contenu
- **Édition en session** : Commande `/memory` pour modifier à la volée

### 2. Outils intégrés massifs 🔧

Claude Code embarque 20+ outils natifs pour l'interaction avec le système :

**Manipulation de fichiers :**
- `Read`, `Write`, `Edit`, `MultiEdit` - Lecture/écriture avancée
- `Glob`, `Grep` - Recherche intelligente dans le codebase
- `LS` - Navigation projet

**Exécution et intégration :**
- `Bash` - Exécution commandes système  
- `WebFetch` - Récupération contenu web
- `Task` - Délégation à des sous-agents spécialisés

**Organisation et mémoire :**
- `TodoWrite` - Gestion de tâches persistante
- `NotebookEdit` - Édition Jupyter notebooks

### 3. Contexte automatique intelligent 🧠

**Indexation projet :** Claude maintient une carte mentale complète du codebase
- Détection automatique de la structure projet
- Recherche contextuelle via `ripgrep` et patterns `glob`
- Inclusion conditionnelle par répertoire

**Recherche adaptative :** L'IA effectue des recherches ciblées selon le contexte
```
Utilisateur: "Quelle fonction implémente l'authentification ?"
Claude: [Recherche automatique] → Lit auth.js → Analyse la fonction login()
```

### 4. Mode Planning et TodoList 📋

**Architecture de planification :**
- **Sous-agent Architect** : Élabore des plans de tâches structurés
- **TodoWrite/Task** : Suivi d'exécution avec statuts (pending, in_progress, completed)
- **Validation étapes** : Confirmation avant actions sensibles

**Exemple de workflow :**
```
Utilisateur: "Ajoute une API de gestion utilisateur"
Claude: [Crée TodoList] → Planifie → Exécute étape par étape → Valide
```

### 5. Hooks et personnalisation avancée ⚙️

**Système de hooks personnalisables :**
- Déclencheurs sur événements (sauvegarde, erreur, etc.)
- Configuration via fichiers de settings
- Intégration avec workflows externes

**MCP (Model Context Protocol) :** Support natif pour extensions externes
- Serveurs de documentation (Notion, Confluence)
- Intégrations outils (Jira, GitHub)
- APIs et bases de données

### 6. Intégration avec frameworks externes 🔗

**Frameworks compatibles Claude Code :**
- **[CCPM](../../frameworks/ccpm/)** - Gestion de projet spec-driven avec GitHub Issues et git worktrees
- **[SuperClaude](../../frameworks/superclaude/)** - Framework avancé pour Claude Code
- **Support MCP natif** - Extensions via Model Context Protocol

---

## 🔍 Découvertes de la communauté

### 1. Phrases déclencheurs de réflexion approfondie ⚡

**Astuce découverte :** Claude Code réagit à certains mots-clés pour ajuster sa profondeur d'analyse :

```markdown
# Déclencheurs confirmés par la communauté
"think harder"           → Mode raisonnement approfondi
"think intensely"        → Analyse plus détaillée  
"think very hard"        → Consommation tokens élevée, qualité maximale
```

**Usage pratique :**
```
❌ "Debug ce problème"
✅ "Think harder about this debugging problem" → Analyse plus systématique
```

### 2. Injection de contexte local avancée 📁

**Techniques communautaires pour forcer le contexte :**

**Méthode 1 - Import CLAUDE.md dynamique :**
```markdown
# Dans CLAUDE.md
@docs/architecture.md
@config/eslint.config.js
@tests/utils.test.js

Tu dois toujours respecter ces conventions...
```

**Méthode 2 - Prompts de démarrage contextuels :**
```markdown
# Contexte : Projet React TypeScript
# Stack : Vite, TailwindCSS, React Query  
# Convention : Functional components + hooks
# Tests : Jest + React Testing Library

Maintenant aide-moi avec...
```

**Méthode 3 - Session préparatoire :**
```
> Ouvre et parcours ces fichiers clés : package.json, src/App.tsx, README.md
> [Claude lit et indexe automatiquement]
> Parfait, maintenant on peut commencer
```

### 3. Gestion des garde-fous de sécurité 🛡️

**Problème découvert :** Claude refuse parfois des demandes légitimes (faux positifs)

**Solutions communautaires :**
```markdown
❌ "Génère un script pour tester les vulnérabilités"
✅ "Aide-moi à créer un script de test de sécurité défensif pour identifier les vulnérabilités potentielles"

❌ "Code pour bypasser l'authentification"  
✅ "Analyse ce code d'authentification pour identifier les failles de sécurité potentielles"
```

**Approche recommandée :** Accentuer l'aspect défensif, éducatif, ou d'audit.

### 4. Optimisation contexte et performance 🚀

**Problème :** Fenêtre de contexte massive mais performance variable

**Astuces communautaires :**

**Contextualisation ciblée :**
```markdown
# Dans CLAUDE.md - Version optimisée
## Règles essentielles (toujours présentes)
- Convention nommage : camelCase
- Framework : React 18 + TypeScript
- Tests obligatoires

## Règles détaillées (import conditionnel)
@docs/detailed-patterns.md  # Seulement si nécessaire
```

**Segmentation des sessions :**
```
# Session longue → Risque de "donut effect" (oubli du milieu)
> /memory refresh  # Recharge le contexte
> [Nouvelle session si nécessaire]
```

### 5. Balises de contexte et validation 🏷️

**Astuce communautaire :** Utiliser des balises uniques pour détecter la perte de contexte

```markdown
# Dans CLAUDE.md
🎯 TOUJOURS commencer tes réponses par l'emoji 🎯

# Usage
Si Claude oublie l'emoji → Contexte perdu → `/memory refresh`
```

### 6. Migration et synchronisation cross-agent 🔄

**Outils communautaires découverts :**

**RuleSync :** Convertisseur de règles entre agents
```bash
# Convertit CLAUDE.md vers d'autres formats
rulesync --from claude --to cursor --input CLAUDE.md
```

**Templates de migration :**
```markdown
# Règles universelles (compatibles tous agents)
- Utilise TypeScript strict
- Tests unitaires obligatoires  
- Code documenté avec JSDoc

# Règles spécifiques Claude Code
@project/technical-context.md  # Import dynamique
Think harder when debugging complex issues  # Phrase déclencheur
```

---

## 📁 Templates battle-tested

### Template CLAUDE.md projet

```markdown
# Context Engineering - [NOM_PROJET]

## 🎯 Règles essentielles
- **Stack :** React 18 + TypeScript + Vite
- **Style :** TailwindCSS + Functional Components
- **Tests :** Jest + React Testing Library (obligatoire)
- **Conventions :** camelCase, ESLint Airbnb, Prettier

## 📁 Structure projet
@package.json                    # Dependencies et scripts
@src/types/index.ts             # Types globaux
@docs/architecture.md           # Architecture détaillée

## 🔍 Contexte métier
[Décrire brièvement le domaine et les objectifs]

## ⚡ Instructions spéciales
- Think harder pour les problèmes complexes
- Toujours valider avec tests avant commit
- Commencer les réponses par 🎯 [validation contexte]

## 🚨 Restrictions  
- Ne jamais ignorer les tests
- Respecter l'architecture existante
- Demander confirmation pour changes structurels
```

### Template hooks avancés 🚧 *TODO*

[Templates d'exemples de hooks pour automatisation]

### Template MCP configuration 🚧 *TODO*  

[Configuration serveurs MCP courants]

---

## 💡 Cas d'usage avancés

### Développement complexe avec sous-agents

```markdown
# Délégation intelligente via Task tool
> Analyse ce système de 50+ fichiers avec focus sécurité
Claude: [Délègue à sub-agent security] → Rapport consolidé
```

### Debug systematique multi-étapes

```markdown
> Think very hard about this performance issue
Claude: [Mode approfondi] → Profiling → Analyse → Recommandations
```

### Context Engineering dynamique

```markdown
# CLAUDE.md évolutif selon phase projet
/scripts/
  setup-context-dev.md      # Phase développement
  setup-context-deploy.md   # Phase déploiement  
  setup-context-debug.md    # Phase debug

# Import conditionnel selon besoin
@scripts/setup-context-debug.md
```

---

## ⚠️ Limitations et contournements

| **Limitation** | **Impact** | **Contournement** |
|----------------|------------|------------------|
| Pas de règles globales simples | Configuration répétée | `~/.claude/CLAUDE.md` + templates |
| Performance variable gros contextes | Lenteur réponses | Segmentation sessions + contexte ciblé |
| Garde-fous parfois trop stricts | Faux positifs sécurité | Reformulation défensive |
| Dépendance réseau pour MCP | Hors-ligne limité | Cache local + fallback |

---

## 🔗 Ressources et communauté

### Documentation officielle
- **[Claude Code Docs](https://docs.anthropic.com/en/docs/claude-code)** - Documentation complète
- **[Anthropic Research](https://www.anthropic.com/research)** - Recherches sur les LLMs

### Outils communautaires  
- **[ClaudeLog.com](https://claudelog.com/)** ⭐ - Documentation communautaire et insights pratiques basés sur l'expérience terrain
- **[RuleSync](https://github.com/rulesync)** - Migration règles entre agents
- **[Claude Code Examples](https://github.com/anthropic/claude-code-examples)** 🚧 *TODO* - Exemples officiels
- **[Community Templates](templates/)** 🚧 *TODO* - Templates partagés

### Intégrations
- **[SuperClaude Framework](../../frameworks/superclaude/)** 🚧 *TODO* - Framework avancé pour Claude
- **[VS Code Extension](https://marketplace.visualstudio.com/items?itemName=Anthropic.claude)** - Extension officielle
- **[CCPM Framework](../../frameworks/ccpm/)** ⭐ - Gestion de projet spec-driven avec GitHub Issues

---

## 🎯 Prochaines étapes

1. **[Installer et configurer](setup-guide.md)** 🚧 *TODO* - Guide d'installation détaillé
2. **[Templates avancés](templates/)** 🚧 *TODO* - Collection de templates prêts à l'emploi  
3. **[Exemples concrets](examples/)** 🚧 *TODO* - Cas d'usage réels détaillés
4. **[Intégration CI/CD](cicd-integration.md)** 🚧 *TODO* - Automatisation avec Claude Code

> 💡 **Astuce finale :** Claude Code excelle dans les contextes complexes. N'hésitez pas à lui fournir beaucoup de contexte structuré - sa large fenêtre contextuelle en fait un atout majeur.