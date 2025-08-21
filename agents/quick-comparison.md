# Comparaison rapide des agents IA 📊

> Vue d'ensemble des capacités de Context Engineering par agent

## 🎯 Guide de choix rapide

| **Si vous voulez...** | **Recommandation** | **Pourquoi ?** |
|----------------------|-------------------|----------------|
| CLI puissant avec reasoning avancé | **Claude Code** 🎯 | Fenêtre contexte énorme, outils intégrés, CLAUDE.md hiérarchique |
| IDE avec UI/UX soignée | **Cursor** ⚡ | Rules sophistiquées, @ contextuel, modes Standard/Max |
| Integration native GitHub | **GitHub Copilot** 🔧 | Repository instructions, organisation policies |
| Open source + customisation | **Gemini CLI** 🌟 | Modifiable, GEMINI.md hiérarchique, quotas généreux |
| Memories automatiques | **Windsurf** 🏄‍♂️ | IA qui se souvient automatiquement, rules conditionnelles |
| Flexibilité maximale | **KiloCode** ⚡ | Rules par mode, support legacy, templates modulaires |
| Méthodologie spec-driven | **Kiro** 🤖 | Steering files, Agent Hooks, développement dirigé par specs |

---

## 📋 Matrice comparative détaillée

### Context Engineering : Capacités de base

| Agent | Règles persistantes | Contexte automatique | Mémoire sessions | Instructions globales |
|-------|-------------------|---------------------|-----------------|---------------------|
| **Claude Code** 🎯 | ✅ `CLAUDE.md` (hiérarchique) | ✅ Indexation projet | ✅ TodoWrite/Tasks | ✅ `~/.claude/CLAUDE.md` |
| **Cursor** ⚡ | ✅ `.cursor/rules/*.md` | ✅ Fichiers ouverts + `@` | ⚠️ Limitée (trimming) | ✅ **User Rules (Settings)** |
| **GitHub Copilot** 🔧 | ✅ `.github/copilot-instructions.md` | ✅ Indexation repo | ❌ Sans état | ✅ Custom Instructions |
| **Gemini CLI** 🌟 | ✅ `GEMINI.md` (hiérarchique) | ✅ MCP + outils | ✅ `/memory show/refresh` | ✅ Global + projet |
| **Windsurf** 🏄‍♂️ | ✅ `.windsurf/rules/` + globales | ✅ Fichiers + context | ✅ **Memories auto** | ✅ Règles globales UI |
| **KiloCode** ⚡ | ✅ `.kilocode/rules/*.md` | ✅ Multi-fichiers | ⚠️ Basic | ✅ Custom Instructions |
| **Kiro** 🤖 | ✅ `.kiro/steering/*.md` | ✅ Références dynamiques | ✅ Specs persistantes | ✅ Enterprise policies |

### Activation intelligente du contexte

| Agent | Règles conditionnelles | Auto-inclusion | Contrôle granulaire | Performance |
|-------|----------------------|----------------|--------------------|--------------|
| **Claude Code** 🎯 | ✅ Par répertoire | ✅ Recherche intelligente | ⚠️ Basique | ⚡⚡⚡ Excellent |
| **Cursor** ⚡ | ⚠️ Mode Standard/Max | ✅ `@` + suggestions | ✅ `.cursorignore` | ⚡⚡ Bon |
| **GitHub Copilot** 🔧 | ✅ `applyTo` frontmatter | ✅ Indexation auto | ⚠️ Filtres org | ⚡⚡ Bon |
| **Gemini CLI** 🌟 | ⚠️ Hiérarchique seulement | ✅ Contextuel | ✅ `contextFileName` | ⚡ Variable |
| **Windsurf** 🏄‍♂️ | ✅ **4 modes activation** | ✅ Memories auto | ✅ UI intégrée | ⚡⚡ Bon |
| **KiloCode** ⚡ | ✅ **Rules par mode** | ✅ Legacy support | ✅ Toggle UI | ⚡⚡ Bon |
| **Kiro** 🤖 | ✅ **3 modes inclusion** | ✅ `#[[file:path]]` | ✅ Steering granulaire | ⚡ Variable |

### Workflow et orchestration

| Agent | Planning/Tasks | Outils intégrés | MCP Support | Extensibilité |
|-------|---------------|----------------|-------------|---------------|
| **Claude Code** 🎯 | ✅ TodoWrite + Tasks | ✅ **20+ outils** | ✅ Natif | ⚠️ Fermé |
| **Cursor** ⚡ | ⚠️ Basic | ✅ Terminal, web | ✅ Support | ⚠️ Fermé |
| **GitHub Copilot** 🔧 | ⚠️ Chat mode | ✅ VS Code intégré | ❌ Limité | ⚠️ Fermé |
| **Gemini CLI** 🌟 | ✅ ReAct (Plan/Act) | ✅ Terminal, web | ✅ Configurables | ✅ **Open source** |
| **Windsurf** 🏄‍♂️ | ⚠️ Cascade chat | ✅ Codeium intégré | ✅ UI intégrée | ⚠️ Fermé |
| **KiloCode** ⚡ | ✅ Workflows auto | ✅ Tests, navigation | ✅ Support | ✅ **Open source** |
| **Kiro** 🤖 | ✅ **Spec-driven dev** | ✅ Agent Hooks | ✅ Privacy-first | ⚠️ Preview |

---

## 🔍 Focus spécialités uniques

### 🌟 **Innovations remarquables**

**Claude Code** 🎯
- **CLAUDE.md hiérarchique** : Global → Projet → Sous-dossier
- **Outils intégrés massifs** : 20+ outils (Bash, WebFetch, Task, etc.)
- **Phrases déclencheurs** : "think harder" active reasoning approfondi

**Windsurf** 🏄‍♂️  
- **Memories automatiques** : IA qui se souvient sans intervention
- **4 modes d'activation** : Always, Manual, IA Decision, Glob patterns

**Kiro** 🤖
- **Steering files modulaires** : product.md, tech.md, structure.md
- **3 modes d'inclusion** : Always, fileMatch, manual (#tag)
- **Agent Hooks** : Triggers automatiques sur événements

**KiloCode** ⚡
- **Rules par mode** : Test, Review, Implementation...
- **Support legacy** : .clinerules, .roorules, etc.

### ⚠️ **Limitations à connaître**

| Agent | Principal défi | Contournement |
|-------|---------------|---------------|
| **Claude Code** | Pas de règles globales simples | Utiliser ~/.claude/CLAUDE.md |
| **Cursor** | Trimming contexte ("donut effect") | Sessions courtes, fichiers pertinents |
| **GitHub Copilot** | Prompt système non modifiable | Repository instructions créatives |
| **Gemini CLI** | Quotas (60/min, 1000/jour) | Prompts groupés, sessions planifiées |
| **Windsurf** | Memories parfois trop agressives | Review périodique des memories |
| **KiloCode** | Interface jeune | Contribution open source active |
| **Kiro** | Preview AWS (instable) | Attendre stabilisation |

---

## 🚀 Recommandations par cas d'usage

### **Développement solo** 
**Claude Code** ou **Cursor** - Excellent équilibre fonctionnalités/performance

### **Équipe/Entreprise**
**GitHub Copilot** (policies org) ou **Kiro** (spec-driven) 

### **Projet open source** 
**Gemini CLI** ou **KiloCode** - Customisation maximale

### **Expérimentation/Learning**
**Windsurf** (memories) ou **KiloCode** (flexibilité)

### **Workflows complexes**
**Claude Code** (outils) ou **Kiro** (hooks + specs)

---

## 🔗 Liens utiles

- **Migrations entre agents** : [Templates cross-platform](../templates/) 🚧 *TODO*
- **Guides détaillés** : 
  - [Claude Code](claude/) 🚧 *TODO*
  - [Cursor](cursor/) 🚧 *TODO* 
  - [GitHub Copilot](github-copilot/) 🚧 *TODO*
  - [Gemini CLI](gemini/) 🚧 *TODO*
  - [Windsurf](windsurf/) 🚧 *TODO*
  - [KiloCode](kilocode/) 🚧 *TODO*
  - [Kiro](kiro/) 🚧 *TODO*
- **Communauté** : [RuleSync](https://github.com/rulesync), [Instructa Prompts](https://github.com/instructa)

> 💡 **Astuce** : La plupart des règles Markdown sont transposables entre agents avec des ajustements mineurs de format.